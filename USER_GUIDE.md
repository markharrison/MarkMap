# UK Alarms Map - User Documentation

## Overview

The UK Alarms Map is a web-based application that displays alarms (items) on an interactive map of the United Kingdom. The application uses LeafletJS for mapping and integrates with the Things API to manage alarm data.

## Features

- **Interactive Map**: View all alarms on an interactive map of the UK
- **Color-coded Status**: Alarms are displayed with different colors based on their status:
  - 🟢 Green: Normal/OK
  - 🟠 Amber: Warning
  - 🔴 Red: Critical/Alert
- **Detailed Information**: Click on any alarm pin to view detailed information in a popup
- **Auto-refresh**: The map automatically updates every 60 seconds to show the latest data
- **Add Alarms**: Create new alarms with custom locations and information
- **Delete Alarms**: Remove alarms that are no longer needed
- **Real-time Statistics**: View total alarm counts and status breakdown in the header

## Getting Started

### Opening the Application

1. Open `index.html` in a modern web browser (Chrome, Firefox, Edge, or Safari)
2. The map will automatically load and display all current alarms
3. The application works entirely in the browser - no installation required

### Viewing the Map

- The map is centered on the UK by default
- Use your mouse to:
  - **Pan**: Click and drag to move around the map
  - **Zoom**: Use the scroll wheel or the +/- buttons in the top-left corner
  - **View Details**: Click on any alarm marker to see its information

## Using the Application

### Viewing Alarm Details

1. Click on any colored pin/marker on the map
2. A popup will appear showing:
   - Alarm name
   - Current status (color-coded)
   - Exact coordinates (latitude/longitude)
   - Description (if available)
   - Image (if available)
3. Click anywhere outside the popup to close it

### Adding a New Alarm

1. Click the **"Add New Alarm"** button at the bottom of the screen
2. Fill in the form:
   - **Name**: Enter a descriptive name for the alarm (required)
   - **Latitude**: Enter the latitude coordinate (UK range: 49 to 61)
   - **Longitude**: Enter the longitude coordinate (UK range: -8 to 2)
   - **Description**: Add any additional information (optional)
   - **Status**: Select the alarm status (Green/Amber/Red)
3. Click **"Add Alarm"** to create the alarm
4. Click **"Cancel"** to close the form without adding
5. The map will automatically refresh to show the new alarm

**Tips for Coordinates:**
- You can use online tools like Google Maps to find coordinates
- Right-click on a location in Google Maps and select the coordinates to copy them
- UK Example coordinates:
  - London: 51.5074, -0.1278
  - Manchester: 53.4808, -2.2426
  - Edinburgh: 55.9533, -3.1883

### Deleting an Alarm

1. Click on the alarm marker you want to delete
2. In the popup, click the **"Delete"** button
3. Confirm the deletion in the dialog that appears
4. Click **"Delete"** to confirm or **"Cancel"** to abort
5. The alarm will be removed from the API and the map will update

### Manual Refresh

While the map automatically updates every 60 seconds, you can manually refresh at any time:

1. Click the **"Refresh Now"** button at the bottom of the screen
2. The application will immediately fetch the latest data from the API
3. The map will update to reflect any changes

## Understanding the Interface

### Header Information

The header displays two key pieces of information:

1. **Alarm Count**: Shows the total number of alarms and breakdown by status
   - Format: `Total: X (🟢 Y | 🟠 Z | 🔴 W)`
   - Example: `Total: 25 (🟢 20 | 🟠 3 | 🔴 2)`

2. **Last Update**: Shows when the data was last refreshed
   - Format: `Last updated: HH:MM:SS`
   - Updates automatically every 60 seconds

### Map Markers

- **Green Marker**: Normal status alarm
- **Orange Marker**: Warning status alarm  
- **Red Marker**: Critical status alarm
- **Marker Shape**: Teardrop/pin shape pointing to the exact location

## Technical Information

### Browser Requirements

- Modern web browser with JavaScript enabled
- Internet connection required
- Supports: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

### Data Source

The application connects to the Things API at:
- **Base URL**: `https://thingsapi.azure1.dev/api/Things`
- **API Documentation**: https://thingsapi.azure1.dev/index.html
- **No Authentication Required**: The API is publicly accessible
- **CORS Enabled**: The API allows cross-origin requests

### Auto-Update Behavior

- The application polls the API every 60 seconds
- Updates are incremental - only changed data is refreshed
- The page does not reload, providing a smooth user experience
- Network errors are logged but don't stop the polling

### Data Privacy

- All data is stored in the Things API, not locally
- No personal information is required to use the application
- Alarm data is public and accessible to all users

## Troubleshooting

### Map Not Displaying

- Check your internet connection
- Ensure JavaScript is enabled in your browser
- Try refreshing the page
- Check the browser console for errors (F12)

### Alarms Not Loading

- Verify internet connectivity
- Check if the API is accessible at https://thingsapi.azure1.dev/api/Things
- Wait for the next auto-refresh (60 seconds)
- Try clicking "Refresh Now"

### Cannot Add Alarm

- Ensure all required fields are filled
- Verify coordinates are within UK range:
  - Latitude: 49 to 61
  - Longitude: -8 to 2
- Check browser console for error messages

### Cannot Delete Alarm

- Ensure you have an active internet connection
- Try refreshing the page and attempting again
- Check browser console for error messages

## Advanced Usage

### Keyboard Shortcuts

- **Escape**: Close open modals
- **+**: Zoom in (when map is focused)
- **-**: Zoom out (when map is focused)

### Mobile Usage

The application is responsive and works on mobile devices:
- Touch to pan the map
- Pinch to zoom
- Tap markers to view details
- All buttons are touch-friendly

## Support and Feedback

For issues, questions, or feedback:
- Check the browser console for technical errors
- Verify API status at https://thingsapi.azure1.dev/index.html
- Review this documentation for common solutions

## Version Information

- **Application**: UK Alarms Map v1.0
- **LeafletJS**: v1.9.4
- **API**: Things API v3.0.1

---

Last updated: January 2026
