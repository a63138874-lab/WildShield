# WildShield — Module Interface Contract

## Purpose
All team members must follow the same function names, input formats, and output formats to avoid integration errors.

## 1. Data Processing
**File:** `data_processor.py`

Function:
`process_report(report: dict) -> dict`

Input: A ranger report containing location, time, and description.

Output: A cleaned report dictionary.

## 2. AI Activity Detection
**File:** `detector.py`

Function:
`analyze_video(video_path: str) -> list[dict]`

Input: Path to an uploaded image or video (image support will be handled separately if needed).

Output: A list of detected objects and their details.

## 3. Risk Analysis
**File:** `risk_engine.py`

Function:
`calculate_risk(detections: list[dict]) -> dict`

Input: Detection results.

Output: A dictionary containing a risk score, risk level, and explanation.

## 4. Event Correlation
**File:** `event_correlation.py`

Function:
`correlate_events(events: list[dict]) -> list[dict]`

Input: Events with timestamps and locations.

Output: Related events grouped by time and location.

## 5. Alert Management
**File:** `alert_manager.py`

Function:
`create_alert(risk_result: dict) -> dict`

Input: Risk analysis result.

Output: An alert dictionary with a unique ID, risk level, reason, and status.

## 6. Risk Map
**File:** `risk_map.py`

Function:
`prepare_map_data(alerts: list[dict]) -> list[dict]`

Input: Alerts with available geographic coordinates.

Output: Map-ready alert locations.

## 7. Officer Verification
**File:** `verification.py`

Function:
`verify_alert(alert_id: str, status: str) -> dict`

Allowed status values: `verified`, `dismissed`, `escalated`.

Output: The updated alert record.

## 8. Frontend Integration
**File:** `app.py`

The frontend must call the exact function names documented above. Do not rename functions or change their parameters without informing the team and updating this document.

## Team Rules
1. Every module must follow this contract.
2. Use dictionaries with consistent key names.
3. Test each module independently before integration.
4. Discuss interface changes with the team before implementing them.
5. Never merge untested code directly into the main branch.
6. AI-generated alerts indicate suspicious activity, not confirmed wildlife crime. An officer must verify them.