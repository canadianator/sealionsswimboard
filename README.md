# 🦁 Sea Lions Swim Meet Board

A modern, self-contained swim meet counter board inspired by the original Gatsby version. Perfect for displaying and controlling swimmer counts at swim competitions.

## 📁 Files Included

Three versions are provided for different use cases:

### 1. **sea-lions-swim-board.html** (Recommended - All-in-One)
Single file with both display and controller modes built-in.
- Toggle between **Display Mode** (full-screen board) and **Controller Mode** (admin panel)
- Perfect for testing or small setups
- **Best for:** Single device or testing

### 2. **sea-lions-display-only.html** (Display Only)
Large-screen display board with two big counters.
- Shows: Bullpen (swimmers up to) and Event (current race number)
- Auto-syncs from localStorage every 500ms
- Shows current time in corner
- **Best for:** Projector/large screen at the pool

### 3. **sea-lions-controller-only.html** (Controller Only)
Clean admin panel for controlling the counters.
- Buttons for incrementing/decrementing both counters
- Keyboard shortcuts for fast control
- Mobile-friendly responsive design
- **Best for:** Tablet/laptop at the control table

## 🚀 Quick Start

### Option 1: Simple Setup (All-in-One)
1. Upload **sea-lions-swim-board.html** to your web server
2. Open in browser
3. Click "⚙ Controller" button to switch to control mode
4. Use the buttons or keyboard shortcuts to update counts
5. Click "View Board ▶" to see the display

### Option 2: Split Display & Control
**On the Display Screen (e.g., projector):**
1. Open **sea-lions-display-only.html**
2. Fullscreen this in your venue

**On the Control Device (e.g., tablet):**
1. Open **sea-lions-controller-only.html**
2. Keep this at the control table
3. Updates will instantly appear on the display screen

### Option 3: Multiple Displays
Use the all-in-one version and:
1. Open **sea-lions-swim-board.html** in display mode on one screen
2. Open the same file in controller mode on another device
3. Both will sync in real-time

## ⌨ Keyboard Shortcuts

The counter responds to arrow keys and Page Up/Page Down with smart multi-tap recognition.

### Single Tap (Within 3 second window)
- **Left Arrow** or **Page Up** → Decrease Bullpen by 1
- **Right Arrow** or **Page Down** → Increase Bullpen by 1

### Double Tap (Within 3 second window)
- **Left Arrow (2x)** → Decrease Event by 1
- **Right Arrow (2x)** → Increase Event by 1

### Triple Tap (Within 3 second window)
- **Left Arrow (3x)** → Decrease both Bullpen and Event by 1
- **Right Arrow (3x)** → Increase both Bullpen and Event by 1

### Button Control
Always available in controller mode and all-in-one mode:
- Use the decrease/increase buttons for each counter
- Quick increment buttons
- Reset to 0 buttons

## 💾 Data Persistence

All counter values are stored in the browser's `localStorage`. This means:
- ✅ Counts persist even if you refresh the page
- ✅ Counts sync across multiple tabs/windows on the same device
- ✅ Counts are device-specific (different devices = different storage)

## 🌐 Hosting on Your Website

### Method 1: Direct HTML File
1. Upload any of the `.html` files to your web server
2. Access via: `https://yourwebsite.com/sea-lions-swim-board.html`
3. Done! No build process needed

### Method 2: Embed in Existing Page
You can embed the display board in an iframe:
```html
<iframe src="/sea-lions-display-only.html" 
        width="100%" 
        height="600" 
        frameborder="0"></iframe>
```

### Method 3: Docker/Container
If using Docker, simply copy the HTML file to your web root:
```dockerfile
FROM nginx:latest
COPY sea-lions-swim-board.html /usr/share/nginx/html/
```

## 📱 Responsive Design

All versions are responsive and work on:
- ✅ Desktop browsers
- ✅ Tablets (iPad, Android tablets)
- ✅ Mobile phones (for testing)
- ✅ Projectors/Large displays
- ✅ Different screen sizes and orientations

## 🎨 Customization

### Change Team Name
Edit the HTML and replace "Sea Lions" with your team name:
```html
<div class="controller-title">🦁 Your Team Name</div>
```

### Change Colors
Edit the CSS variables:
```css
:root {
  --bullpen-color: rgb(37, 55, 74);    /* Left counter color */
  --event-color: rgb(30, 115, 190);    /* Right counter color */
  ...
}
```

### Change Emoji/Icon
Replace the 🦁 emoji with your team's logo or icon.

## 🔄 Browser Compatibility

Works on all modern browsers:
- ✅ Chrome/Chromium
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Mobile browsers

## 🛠 Technical Details

- **Technology:** Plain HTML, CSS, JavaScript (no frameworks needed)
- **Dependencies:** None! Completely self-contained
- **Storage:** Browser localStorage
- **Size:** ~15-20KB per file (very fast loading)
- **Performance:** Optimized for low latency, smooth updates

## ⚠ Important Notes

1. **Same Browser/Device:** If using separate display and controller devices, they must access the same localStorage. For web apps on the same network, use the localStorage sync (built-in). For completely separate networks, consider using a backend service.

2. **Data Privacy:** All data is stored locally in the browser. No information is sent to external servers.

3. **Persistence:** Data only persists within the same browser on the same device. Clearing browser cache will reset counters.

4. **Multi-Tab Sync:** If you open the same file in multiple tabs on one device, they will sync automatically (every 500ms).

## 🐛 Troubleshooting

### Counters not showing up on display?
- Make sure both devices have the page open in the same browser
- Check that JavaScript is enabled
- Try a hard refresh (Ctrl+F5 or Cmd+Shift+R)

### Keyboard shortcuts not working?
- Make sure the page has focus (click on it)
- Try using Page Up/Page Down instead of arrow keys if arrows don't work
- Check that NumLock is on if using numeric keypad

### Counts reset when I refresh?
- This is normal if localStorage is cleared
- Try opening in a private/incognito window (storage should persist during the session)

### Mobile buttons are too small?
- The interface is responsive; it should adjust automatically
- Try pinching to zoom if needed
- Controller-only version has larger buttons than combined version

## 📚 Original Project

This is a modern web-based version of:
https://github.com/Sammons/sea-lions-swim-board

The original used Gatsby/React. This version uses plain HTML/CSS/JS for easier hosting and deployment.

## 📝 License

MIT License - Feel free to use, modify, and distribute for your swim team!

## 🎯 Tips for Best Results

1. **Fullscreen the display:** Use browser fullscreen (F11) on the projector display
2. **Use keyboard shortcuts:** Fastest way to update counts during active swimming
3. **Keep controller device charged:** Keep your control tablet on during the meet
4. **Test before race day:** Make sure all devices are syncing properly
5. **Simple design:** The large numbers are intentionally simple for visibility from far away

## 💬 Feedback

If you find issues or have feature requests, feel free to improve these files for your needs!

Happy swimming! 🏊‍♂️🏊‍♀️
