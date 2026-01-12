# Quick Start Guide

## What is MarkMap?

MarkMap is a web-based application that displays alarms (monitoring items) on an interactive map of the United Kingdom. It's designed for monitoring and managing geographically distributed alarms with real-time updates.

## Getting Started in 3 Steps

1. **Open the Application**
   ```
   Simply open index.html in any modern web browser
   ```

2. **View Alarms**
   - The map loads automatically showing all active alarms
   - Click any colored pin to see details
   - Different colors indicate different status levels

3. **Manage Alarms**
   - Click "Add New Alarm" to create a new monitoring point
   - Click "Delete" in any alarm popup to remove it

## Key Features

✅ **No Installation Required** - Pure HTML/CSS/JavaScript  
✅ **Real-Time Updates** - Auto-refreshes every 60 seconds  
✅ **Color-Coded Status** - Green (OK), Amber (Warning), Red (Critical)  
✅ **Interactive Map** - Pan, zoom, and explore  
✅ **Full CRUD Operations** - Create and delete alarms  
✅ **Mobile Friendly** - Responsive design  
✅ **Secure** - Passed security scans, input validation  

## File Overview

| File | Purpose |
|------|---------|
| `index.html` | Main application page - open this file |
| `styles.css` | Visual styling and layout |
| `app.js` | Application logic and API integration |
| `README.md` | Project documentation |
| `USER_GUIDE.md` | Detailed usage instructions |
| `TESTING.md` | Testing checklist |

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for map tiles and API)

## API Information

The application connects to the Things API:
- **URL**: https://thingsapi.azure1.dev/api/Things
- **Documentation**: https://thingsapi.azure1.dev/index.html
- **No Authentication Required**

## Need Help?

1. See [USER_GUIDE.md](USER_GUIDE.md) for detailed instructions
2. See [TESTING.md](TESTING.md) for testing checklist
3. Check browser console (F12) for error messages
4. Verify API is accessible at https://thingsapi.azure1.dev

## Example Coordinates (UK)

- **London**: 51.5074, -0.1278
- **Manchester**: 53.4808, -2.2426
- **Edinburgh**: 55.9533, -3.1883
- **Cardiff**: 51.4816, -3.1791
- **Belfast**: 54.5973, -5.9301

## Security

✓ All user input is sanitized  
✓ XSS prevention measures in place  
✓ URL validation for images  
✓ Passed CodeQL security analysis  

## License

MIT License - See LICENSE file

---

**Ready to start?** Just open `index.html` in your browser!
