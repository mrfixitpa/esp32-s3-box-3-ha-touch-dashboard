# Changelog

## v0.1.5
- Performance: idle screen now uses a solid light-blue background instead of redrawing a full-screen PNG
- Added low-cost accent divider lines under the header (no image blitting)
- Includes prior v0.1.4 fixes (12/24h toggle logic, wake-word model cleanup, layout polish)

## v0.1.4
- Polished idle layout: moved date and button row up for better vertical balance
- HVAC status icon is inline before the “Indoor Temp” label
- “Indoor Temp” header uses a bolder font for improved readability

## v0.1.3
- Idle header simplified: smaller **Indoor Temp** label aligned left
- Removed the solid black header bar so `idle.png` fills the top of the screen
- Improved button visibility for straight-on viewing:
  - OFF buttons match clock color for quick glances
  - ON buttons use high-contrast **amber** ring + icon

## v0.1.2
- Increased idle button visibility (stronger rings / contrast)
- Added clock horizontal offset control
- Idle background uses `idle.png`

## v0.1.0 – v0.1.1
- Initial project bring-up and stability fixes
