# WebMap Testing Guide

This document provides testing instructions for the UK Alarms Map application.

## Manual Testing Checklist

### Setup
- [ ] Open `index.html` in a modern web browser
- [ ] Verify the page loads without console errors
- [ ] Check that the map displays correctly

### Map Display
- [ ] Verify map is centered on UK (approximately lat: 54.5, lng: -3.5)
- [ ] Test zoom controls (+/- buttons)
- [ ] Test panning by dragging the map
- [ ] Verify markers appear for all alarms

### Marker Colors
- [ ] Green markers for status="green"
- [ ] Orange markers for status="amber"
- [ ] Red markers for status="red"

### Popup Information
- [ ] Click on a marker to open popup
- [ ] Verify alarm name is displayed
- [ ] Verify status is shown with correct color
- [ ] Verify coordinates are displayed
- [ ] Verify description appears (if present)
- [ ] Verify image appears (if present and valid URL)
- [ ] Test Delete button appears in popup

### Auto-Refresh
- [ ] Wait 60 seconds and verify "Last updated" time changes
- [ ] Verify map updates without page reload
- [ ] Check that alarm count updates if data changes

### Add Alarm
- [ ] Click "Add New Alarm" button
- [ ] Verify modal dialog opens
- [ ] Fill in all fields:
  - Name: "Test Alarm"
  - Latitude: 51.5074 (London)
  - Longitude: -0.1278
  - Description: "Test description"
  - Status: Red
- [ ] Click "Add Alarm"
- [ ] Verify success message appears
- [ ] Verify new marker appears on map
- [ ] Verify alarm count increases

### Add Alarm - Validation
- [ ] Try submitting form with empty name (should fail)
- [ ] Try latitude outside range (e.g., 70) (should fail HTML5 validation)
- [ ] Try longitude outside range (e.g., 10) (should fail HTML5 validation)
- [ ] Test Cancel button closes modal

### Delete Alarm
- [ ] Click on any alarm marker
- [ ] Click Delete button in popup
- [ ] Verify confirmation dialog appears
- [ ] Verify alarm name is shown in confirmation
- [ ] Click "Delete" to confirm
- [ ] Verify success message appears
- [ ] Verify marker disappears from map
- [ ] Verify alarm count decreases

### Delete Alarm - Cancel
- [ ] Click on any alarm marker
- [ ] Click Delete button
- [ ] Click "Cancel" in confirmation dialog
- [ ] Verify alarm is NOT deleted
- [ ] Verify marker remains on map

### Manual Refresh
- [ ] Click "Refresh Now" button
- [ ] Verify "Last updated" time changes immediately
- [ ] Verify map data refreshes

### Statistics Display
- [ ] Verify header shows total alarm count
- [ ] Verify breakdown by status (green/amber/red counts)
- [ ] Verify counts update after add/delete operations

### Responsive Design
- [ ] Resize browser window to mobile size (< 768px)
- [ ] Verify buttons stack vertically
- [ ] Verify modal is properly sized
- [ ] Verify map remains functional
- [ ] Test on actual mobile device if possible

### Error Handling
- [ ] Disconnect network and click Refresh
- [ ] Verify error message appears
- [ ] Verify application remains functional after error
- [ ] Reconnect and verify recovery

### Security Testing
- [ ] Try adding alarm with name containing HTML: `<script>alert('xss')</script>`
- [ ] Verify HTML is escaped and rendered as text
- [ ] Try adding alarm with special characters in name: `Test's "Alarm" & More`
- [ ] Verify characters are handled correctly

### Cross-Browser Testing
Test in multiple browsers:
- [ ] Chrome/Chromium
- [ ] Firefox
- [ ] Safari (if on macOS)
- [ ] Edge

### Performance
- [ ] Verify page loads quickly (< 2 seconds)
- [ ] Verify no lag when interacting with map
- [ ] Check browser console for errors or warnings
- [ ] Verify memory usage is reasonable over time

## API Testing

You can also test the API directly using curl:

```bash
# Get all alarms
curl https://thingsapi.azure1.dev/api/Things

# Add a new alarm
curl -X POST https://thingsapi.azure1.dev/api/Things \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Test Alarm",
    "latitude": 51.5074,
    "longitude": -0.1278,
    "text": "Test description",
    "status": "green",
    "image": "",
    "data": ""
  }'

# Delete an alarm (replace {id} with actual ID)
curl -X DELETE https://thingsapi.azure1.dev/api/Things/{id}
```

## Expected Behavior Summary

1. **Initial Load**: Map displays with all existing alarms as colored markers
2. **Auto-Update**: Every 60 seconds, data refreshes without page reload
3. **Add Alarm**: Creates new marker on map immediately after API call
4. **Delete Alarm**: Removes marker from map immediately after API call
5. **Validation**: Form prevents invalid coordinate submissions
6. **Error Handling**: Network errors are logged and displayed to user
7. **Security**: All user input is properly escaped and validated

## Known Limitations

1. No authentication - API is publicly accessible
2. No undo functionality for deletions
3. No edit functionality (must delete and recreate)
4. No search/filter functionality
5. Images from external URLs may not load if blocked by CORS

## Troubleshooting

If you encounter issues:

1. **Map not loading**: Check browser console for CDN loading errors
2. **API errors**: Verify https://thingsapi.azure1.dev is accessible
3. **Markers not appearing**: Check that alarms have valid lat/lng coordinates
4. **Form not submitting**: Check browser console for validation errors

## Test Results

Document your test results here:

Date: ___________
Tester: ___________
Browser: ___________

Test Results:
- Setup: PASS / FAIL
- Map Display: PASS / FAIL
- Markers: PASS / FAIL
- Popups: PASS / FAIL
- Add Alarm: PASS / FAIL
- Delete Alarm: PASS / FAIL
- Auto-Refresh: PASS / FAIL
- Responsive: PASS / FAIL
- Security: PASS / FAIL

Notes:
_________________________________
_________________________________
_________________________________
