# MarkMap

A web-based application for displaying and managing alarms on an interactive map of the United Kingdom.

## Overview

MarkMap is a simple, lightweight web application that displays items (alarms) on an interactive map using LeafletJS. It integrates with the Things API to provide real-time alarm monitoring and management capabilities.

## Features

- 🗺️ **Interactive UK Map**: Navigate and explore alarms across the UK
- 📍 **Visual Markers**: Color-coded pins based on alarm status (Green/Amber/Red)
- ℹ️ **Detailed Information**: Click markers for comprehensive alarm details
- 🔄 **Auto-Refresh**: Automatic updates every 60 seconds
- ➕ **Add Alarms**: Create new alarms with custom locations and details
- 🗑️ **Delete Alarms**: Remove alarms through the web interface
- 📊 **Real-time Statistics**: View alarm counts and status breakdown
- 📱 **Responsive Design**: Works on desktop and mobile devices

## Quick Start

1. Open `index.html` in a web browser
2. The map will load automatically with all current alarms
3. Click on markers to view details
4. Use the "Add New Alarm" button to create alarms
5. Use the "Refresh Now" button for manual updates

## Technology Stack

- **HTML5**: Semantic markup
- **CSS3**: Modern styling with animations
- **Vanilla JavaScript**: No frameworks required
- **LeafletJS v1.9.4**: Interactive maps
- **OpenStreetMap**: Map tiles
- **Things API**: Backend data source

## API Integration

The application integrates with the Things API:
- **Endpoint**: https://thingsapi.azure1.dev/api/Things
- **API Docs**: https://thingsapi.azure1.dev/index.html
- **Authentication**: None required
- **CORS**: Enabled

### API Operations

- `GET /api/Things` - Retrieve all alarms
- `POST /api/Things` - Create a new alarm
- `DELETE /api/Things/{id}` - Delete an alarm by ID

## File Structure

```
MarkMap/
├── index.html       # Main HTML file
├── styles.css       # Application styles
├── app.js          # JavaScript logic
├── USER_GUIDE.md   # Detailed user documentation
└── README.md       # This file
```

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

Internet connection required for map tiles and API access.

## Documentation

For detailed usage instructions, see [USER_GUIDE.md](USER_GUIDE.md)

## License

This project uses the MIT License (see repository LICENSE file).

The Things API is provided by Mark Harrison under the MIT License.
