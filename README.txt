October 2026 V3 - Option 2 implemented

This revision keeps the student attendance constraints hard and relaxes Kru Baipak only if needed.

Kru Baipak rule
- Prefer 3 adjacent periods whenever Kru Baipak comes.
- Preferred blocks are T1-T2-T3, T2-T3-T4, or T3-T4-T5.
- If required by the timetable, a 2-period adjacent visit is allowed.
- Allowed 2-period blocks are T1-T2, T2-T3, T3-T4, or T4-T5.
- A 1-period visit is not allowed.
- Separated periods on the same visit are not allowed.
- In the timetable in this package, Kru Baipak actually receives 3 adjacent periods on every visit, so the relaxation did not need to be used.

Student attendance
- Core student pathways have no more than 4 periods in one day.
- No student pathway may require attendance for more than 4 consecutive calendar days.
- EFC is included when checking consecutive attendance days.
- EFC remains an optional additional course and is not used to change the core pathway daily-period cap.
- Three distinct-subject days use T1-T2-T3 or T2-T3-T4.
- Repeated subjects are limited to 2 periods on the same day and must use an allowed adjacent pair.

P5
- P5 pathways are MP5 + SP5 + EPF or MP5 + SP5 + EPA.
- MP5, SP5, EPF, and EPA are scheduled only on Monday, Wednesday, and Friday.
- Repeated lessons are used where required to reach the requested course totals.

Other hard constraints retained
- Maximum 3 classrooms in use at the same time.
- No teacher overlaps.
- Full-time teachers teach no more than 4 periods per day.
- Full-time teachers work no more than 25 days.
- Kru Lek has no Saturday lessons.
- Kru Base stays within the permitted dates and time windows.
- CM5 remains 8 periods.
- All requested course-period totals are met.

Web app
- Works when index.html is opened directly from a computer.
- Same-period lessons are displayed side by side in multiple columns.
- Teacher and student-path views are included.
- EFC overlay is included.
- PNG export and browser Save as PDF are included.


PNG export - native canvas renderer
- The PNG exporter no longer screenshots HTML.
- It draws the current timetable view directly from the schedule data onto a Canvas.
- This avoids Safari SVG foreignObject, html2canvas, local-file, and off-screen DOM capture failures.
- It can export the complete month even when the full calendar is larger than the browser viewport.
- Overview, Teacher, Student, and EFC state are reflected in the exported image.
- Same-period classes are drawn as multiple columns.
- Summary cards and schedule checks are included.
- PNG export has no external JavaScript dependency and works offline.


Reliable image export
- Replaced PNG/canvas capture with a direct vector SVG export.
- SVG is a real image format and captures the complete current timetable UI regardless of viewport size.
- No canvas, screenshot, foreignObject, html2canvas, CDN, or rasterisation is used.
- This avoids Safari canvas-size and blank-image failures.
- The SVG can be opened in Safari, Chrome, Preview-compatible apps, design tools, or converted to PNG later if needed.
- PDF export remains available via browser Save as PDF.


Student pathway multi-select
- Student view now supports selecting multiple pathways at the same time.
- The selector uses checkbox options inside a dropdown so combinations can be toggled without Ctrl/Cmd-click.
- When more than one pathway is selected, each pathway receives a unique outline color.
- Courses shared by two or more selected pathways use a grey outline.
- Grey is reserved for shared courses and is never assigned to a pathway.
- If EFC is enabled while multiple pathways are shown, EFC is treated as shared and receives the grey outline.
- A pathway legend appears only when multiple pathways are selected.
- SVG export carries the same pathway outlines and shared-course grey rule.
