# 👥 CollaborativeHire: User Stories (INVEST-Compliant)

---

## 📖 User Story 1: Recruiter Views Real-Time Candidate Status Updates

**Persona:** **Sarah Chen**, Talent Acquisition Manager
- Experience: 3 years in recruiting
- Context: Managing 20+ open positions with daily hiring activity
- Pain Point: Constantly checking emails to track candidate progress; misses updates from hiring managers

---

**Title:** View real-time candidate status updates without manual refresh

**Story:**
```
As a recruiter,
I want to see live updates of candidate status changes (e.g., "Passed screening", "Interview scheduled")
so that I always know where each candidate stands without sending follow-up emails.
```

---

## ✅ Acceptance Criteria (BDD)

1. **Given** Sarah is viewing the candidate pipeline dashboard,
   **When** a hiring manager moves a candidate to the next stage,
   **Then** Sarah sees the status update appear on her screen within 1 second (no page refresh needed).

2. **Given** Sarah is viewing Candidate #45's profile,
   **When** an interviewer submits feedback,
   **Then** the feedback appears instantly in the "Interview Feedback" section with the interviewer's name and timestamp.

3. **Given** Sarah has multiple browser tabs open (Slack, email, ATS dashboard),
   **When** a candidate status changes,
   **Then** Sarah receives a visual notification badge (blue dot) on the browser tab showing the ATS is updated.

4. **Given** Sarah's internet connection drops and reconnects,
   **When** she regains connection,
   **Then** the dashboard syncs to the latest state automatically (no manual refresh required).

---

## 📌 Additional Notes
- Real-time updates should work across multiple simultaneous users viewing the same candidate
- Notification should persist until Sarah clicks the updated status
- Should work on desktop and mobile views
- No performance degradation with 100+ candidates in view

## 📊 Metadata
- **Priority:** High
- **Story Points:** 3
- **INVEST Check:** ✅ Independent | ✅ Negotiable | ✅ Valuable | ✅ Estimable | ✅ Small | ✅ Testable

---

═══════════════════════════════════════════════════════════════════════════

---

## 📖 User Story 2: Hiring Manager Provides Structured Interview Feedback

**Persona:** **Mike Rodriguez**, Engineering Manager
- Experience: 7 years as a manager; first time using ATS
- Context: Conducting 3 interviews per week; needs to quickly record observations
- Pain Point: Lengthy feedback forms slow him down; loses detailed notes when not submitted immediately

---

**Title:** Submit quick structured interview feedback within 2 minutes

**Story:**
```
As a hiring manager,
I want to submit interview feedback using a simple form with scoring and comments,
so that I can record my assessment immediately after an interview without lengthy data entry.
```

---

## ✅ Acceptance Criteria (BDD)

1. **Given** Mike has just finished an interview and opens the candidate profile,
   **When** he clicks "Add Interview Feedback",
   **Then** a simple form appears with fields: Technical Score (1-5), Communication (1-5), Recommendation (Hire/Maybe/No Hire), and Comments.

2. **Given** Mike is filling out the feedback form,
   **When** he selects a score or option,
   **Then** the form saves his selections to a local draft (auto-save) in case his browser closes.

3. **Given** Mike has completed the feedback form,
   **When** he clicks "Submit Feedback",
   **Then** the feedback is saved and appears instantly in the candidate's profile, visible to the recruiter (Sarah).

4. **Given** Mike is on a mobile device after an interview,
   **When** he opens the feedback form,
   **Then** all form fields are clearly visible and easy to tap (no horizontal scrolling required).

---

## 📌 Additional Notes
- Feedback submission should take < 2 minutes total (form should have 4-5 fields max)
- Provide optional character limit on comments (e.g., 500 characters) with counter
- Display average score across all interviewers on candidate profile
- Do NOT require Mike to navigate multiple pages or modals

## 📊 Metadata
- **Priority:** High
- **Story Points:** 2
- **INVEST Check:** ✅ Independent | ✅ Negotiable | ✅ Valuable | ✅ Estimable | ✅ Small | ✅ Testable

---

═══════════════════════════════════════════════════════════════════════════

---

## 🔍 Story Analysis & Relationships

### Independence Check ✅
- **Story 1** (Sarah views updates) does NOT depend on **Story 2** (Mike submits feedback)
- Mike's feedback can be submitted through a different system if needed
- Sarah's dashboard can display other status updates (interviews scheduled, assessments completed) independently

### Value Delivery
- **Story 1:** Reduces recruiter email volume by 70%; improves visibility
- **Story 2:** Reduces hiring manager friction; enables faster decision-making

### Sprint Fit
- **Story 1:** 3 points (includes WebSocket setup, real-time sync, notifications)
- **Story 2:** 2 points (form UI, auto-save, validation)
- **Combined:** 5 points = approximately 1-2 days for experienced team

---

## 📋 Definition of Done (For Both Stories)

- ✅ Code reviewed and approved by 2+ team members
- ✅ All acceptance criteria verified and passing
- ✅ Tested on Chrome, Firefox, Safari, and mobile (iOS/Android)
- ✅ No console errors or warnings
- ✅ Accessibility: WCAG 2.1 AA compliant (keyboard navigation, screen reader tested)
- ✅ Performance: Page load < 2 seconds; real-time updates < 500ms latency
- ✅ User tested with 2+ real users from target persona
- ✅ Documentation/help text updated if applicable


═══════════════════════════════════════════════════════════════════════════



# 🎫 Sprint Tickets: Real-Time Candidate Status Updates (User Story #1)

---

## 🎫 Ticket #1: Design Real-Time Dashboard UI Mockups

### 1. 📋 Description
**Purpose:** Create visual designs for the real-time candidate pipeline dashboard that shows live status updates and notifications. This establishes the UI contract for frontend and backend teams.

**Details:**
- Design the candidate pipeline dashboard with status columns (Applied, Screening, Phone Screen, Interview, Offer, Hired)
- Show candidate cards that update in real-time without visual flicker
- Design notification badge (blue dot) on updated candidates
- Design visual indicator showing "Last updated 2 seconds ago"
- Show interviewer presence (who else is viewing this dashboard)
- Ensure design works on desktop (1920px) and mobile (375px) viewports
- Define color scheme for status changes (e.g., green pulse for new update)

---

### 2. ✅ Acceptance Criteria
- [ ] Figma/design file with 3+ dashboard states (idle, updating, multiple updates)
- [ ] Component library showing status change animations (fade-in, pulse effects)
- [ ] Notification badge design (color, size, position consistency)
- [ ] Mobile responsive mockup verified at 375px and 768px widths
- [ ] Design spec document with timing requirements (1s update latency)
- [ ] Accessibility checklist: WCAG AA color contrast ratios verified

**Validation steps:**
1. Design reviewed and approved by Product Manager and Frontend Lead
2. Figma file shared with development team with components linked
3. All states and edge cases documented (loading, error, offline states)

---

### 3. 🚨 Priority
🔴 High — This is the first step; blocks frontend development

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 2
- **Estimated Time:** 4–6 hours

---

### 5. 👤 Assignment
- **Team/Role:** UX/UI Designer
- **Suggested Assignee:** Senior UX Designer

---

### 6. 🏷️ Labels / Tags
- **Type:** Design
- **Area:** UI
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use design tokens from existing component library (colors, spacing, typography)
- Ensure animations are accessible (respect `prefers-reduced-motion`)
- Consider low-bandwidth scenarios (fade-in vs. flashy animations)

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #2 (Frontend Component Implementation)
- **External Docs/Designs:** Figma project link (TBD)

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #2: Implement WebSocket Server Infrastructure

### 1. 📋 Description
**Purpose:** Set up the WebSocket server that will handle real-time connections from multiple dashboard viewers, enabling bidirectional communication between frontend clients and backend event streams.

**Details:**
- Choose WebSocket library (Socket.io or native WebSocket + custom management)
- Implement connection pool management (track active connections per organization/user)
- Implement authentication middleware (verify JWT token on WebSocket upgrade)
- Implement namespace/room management (each job/dashboard is a "room")
- Handle connection lifecycle: connect, disconnect, timeout (5 min idle), reconnect
- Implement heartbeat/ping-pong every 30 seconds to detect dead connections
- Log all connection events (connect, disconnect, errors) for monitoring

---

### 2. ✅ Acceptance Criteria
- [ ] WebSocket server starts and listens on port 3001 (or configured port)
- [ ] JWT authentication required on connection upgrade (rejects invalid tokens)
- [ ] Connection pool tracks active connections by organization_id and user_id
- [ ] Heartbeat mechanism detects and cleans up dead connections every 5 minutes
- [ ] Server can handle 10,000+ concurrent connections without memory leaks
- [ ] All connection events logged to CloudWatch/ELK with request ID tracing
- [ ] Graceful shutdown: existing connections drain before termination (30-second timeout)

**Validation steps:**
1. Load test: 100 concurrent WebSocket connections → verify no memory leaks over 1 hour
2. Verify JWT validation rejects tokens with invalid signatures
3. Check connection pool cleanup: simulate client disconnect → verify freed from pool within 10 seconds
4. Monitor logs for connection trace IDs on Connect, Disconnect, Error events

---

### 3. 🚨 Priority
🔴 High — Critical infrastructure dependency

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 5
- **Estimated Time:** 1–1.5 days

---

### 5. 👤 Assignment
- **Team/Role:** Backend Engineer (Infrastructure/DevOps)
- **Suggested Assignee:** Senior Backend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature (Infrastructure)
- **Area:** Backend / DevOps
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Consider using Socket.io for built-in reconnection logic and rooms support
- Ensure connection pooling handles multi-region/multi-server deployments
- Document WebSocket message format for API contract (separate Ticket #3)

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #3 (WebSocket Event API), #4 (Redis Pub/Sub), #9 (Frontend WebSocket Client)
- **External Docs/Designs:** Socket.io documentation, WebSocket RFC 6455

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #3: Define WebSocket Event API & Message Schema

### 1. 📋 Description
**Purpose:** Document the contract for all real-time events flowing through WebSocket. This ensures frontend and backend teams work to the same specification.

**Details:**
- Define event schema for status changes: `{ event_type, application_id, old_status, new_status, changed_by_user_id, timestamp }`
- Define event schema for feedback submission: `{ event_type, application_id, feedback_id, interviewer_id, scores, timestamp }`
- Define event schema for presence updates: `{ event_type, user_id, viewing_application_id, is_online, timestamp }`
- Define error messages: `{ error_code, error_message, recoverable }`
- Define ack/confirmation messages for client-to-server events
- Define subscription/room messages (client joins "job_123_dashboard")
- Document message ordering guarantees (at-least-once, idempotency keys)

---

### 2. ✅ Acceptance Criteria
- [ ] OpenAPI/AsyncAPI documentation file created with all event schemas
- [ ] JSON schema files created for validation (TypeScript types generated)
- [ ] All events include: event_id (UUID for deduplication), timestamp (ISO 8601), version (schema version)
- [ ] Backward compatibility documented (how to handle schema changes)
- [ ] Example payloads provided for all 5+ event types
- [ ] Error codes and recovery strategies documented
- [ ] Reviewed and approved by Backend Lead and Frontend Lead

**Validation steps:**
1. Schema file validates against OpenAPI 3.0 spec
2. TypeScript types auto-generated from schema without errors
3. All event types tested in isolated unit tests

---

### 3. 🚨 Priority
🔴 High — Blocks concurrent development of #2, #4, #9

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 2
- **Estimated Time:** 3–4 hours

---

### 5. 👤 Assignment
- **Team/Role:** Backend Architect / Technical Writer
- **Suggested Assignee:** Senior Backend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Task (Specification)
- **Area:** API / Backend
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use existing API schema patterns from REST API for consistency
- Include example scenarios (e.g., "Recruiter updates status while HM viewing dashboard")
- Consider message versioning for future schema evolution

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #2 (WebSocket Server), #4 (Event Publishing), #9 (Frontend WebSocket Client)
- **External Docs/Designs:** AsyncAPI spec (https://www.asyncapi.com/), OpenAPI 3.0

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #4: Implement Redis Pub/Sub for Event Distribution

### 1. 📋 Description
**Purpose:** Set up Redis Pub/Sub to distribute real-time events across multiple backend services and WebSocket servers. This allows events generated in one service (e.g., Application Service updating status) to be broadcast to all connected clients.

**Details:**
- Configure Redis client connection with connection pooling
- Implement publisher: Application Service publishes events to Redis channels (e.g., `app:updates`, `feedback:updates`)
- Implement subscriber: WebSocket server subscribes to Redis channels and broadcasts to connected clients
- Implement channel naming convention (e.g., `job:{job_id}:updates` for job-specific events)
- Handle Redis connection failures with exponential backoff and reconnection
- Ensure Redis message ordering (use ordered streams if needed)
- Monitor Redis pub/sub subscriptions and throughput

---

### 2. ✅ Acceptance Criteria
- [ ] Redis connection established with 10 concurrent connections pool
- [ ] Application Service publishes status change events to Redis: `app:status:updated` channel
- [ ] Application Service publishes feedback events to Redis: `app:feedback:submitted` channel
- [ ] WebSocket server subscribes to channels and receives events within 100ms
- [ ] Events include idempotency keys (event_id) to prevent duplicate processing
- [ ] Connection failures trigger exponential backoff retry (max 5 retries, 2-30 second delay)
- [ ] Redis metrics available: subscriptions count, messages/sec, latency percentiles
- [ ] No message loss during normal operation (verified in integration tests)

**Validation steps:**
1. Publish test event to Redis → verify WebSocket server receives within 100ms
2. Simulate Redis disconnection → verify automatic reconnection and message catchup
3. Load test: 1000 events/sec through Redis → verify latency <100ms p99
4. Monitor Redis memory usage over 1 hour sustained event load

---

### 3. 🚨 Priority
🔴 High — Required for real-time event delivery

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 3
- **Estimated Time:** 1 day

---

### 5. 👤 Assignment
- **Team/Role:** Backend Engineer (Infrastructure)
- **Suggested Assignee:** Backend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature (Infrastructure)
- **Area:** Backend / Infrastructure
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Consider Redis Streams alternative if at-least-once delivery becomes critical
- Document Redis failover strategy (sentinel or cluster mode for production)
- Ensure channel names are consistent across all services

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #2 (WebSocket Server), #5 (Application Status Event Publishing)
- **External Docs/Designs:** Redis Pub/Sub documentation, Redis client library (Node-Redis or ioredis)

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #5: Implement Application Status Change Event Publishing

### 1. 📋 Description
**Purpose:** Update the Application Service to emit real-time events whenever a candidate's application status changes (e.g., from "screening" to "interview"). This is the trigger for all downstream real-time updates.

**Details:**
- Modify application status update endpoint to emit event after status change committed to DB
- Event must include: application_id, old_status, new_status, changed_by_user_id, timestamp
- Publish event to Redis `app:status:updated` channel
- Event must be published **after** database transaction commits (ensure consistency)
- Handle edge case: concurrent status updates (last-write-wins with timestamp validation)
- Log event publication with application_id for audit trail
- Ensure event publishing doesn't block the API response (use background job if needed)

---

### 2. ✅ Acceptance Criteria
- [ ] Status update endpoint publishes event to Redis immediately after DB commit
- [ ] Event payload includes all required fields (application_id, old_status, new_status, user_id, timestamp)
- [ ] Event published within 50ms of DB commit (non-blocking)
- [ ] Concurrent status updates handled correctly (no race conditions)
- [ ] Failed event publication doesn't cause API response error (graceful degradation)
- [ ] Event publishing tested with unit tests (mock Redis)
- [ ] Integration test verifies event reaches WebSocket subscribers within 100ms

**Validation steps:**
1. Update candidate status via API → verify event appears in Redis
2. Concurrent updates from multiple clients → verify correct status in DB and event published
3. Redis publish fails → verify API still returns success (event queued for retry)

---

### 3. 🚨 Priority
🔴 High — Core data flow for real-time updates

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 3
- **Estimated Time:** 1 day

---

### 5. 👤 Assignment
- **Team/Role:** Backend Engineer (Application Service Owner)
- **Suggested Assignee:** Backend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Backend / API
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Consider idempotency: same status update called twice should only publish once
- Ensure database transaction includes event publishing commit (transactional guarantee)
- Document event schema in Ticket #3

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #4 (Redis Pub/Sub), #3 (Event Schema)
- **External Docs/Designs:** Application Service code (TBD)

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #6: Implement Interview Feedback Event Publishing

### 1. 📋 Description
**Purpose:** Update the Interview/Feedback endpoint to emit real-time events when an interviewer submits feedback. This allows recruiters to see feedback appear instantly on the candidate profile.

**Details:**
- Modify feedback submission endpoint to publish event after feedback saved to DB
- Event must include: application_id, feedback_id, interviewer_user_id, scores, timestamp
- Publish event to Redis `app:feedback:submitted` channel
- Event published atomically with DB transaction (within same commit)
- Handle edge case: feedback updates (not just creation) should also trigger events
- Log feedback event publication with application_id and interviewer_id
- Ensure feedback privacy: only notify relevant users (recruiters, hiring managers)

---

### 2. ✅ Acceptance Criteria
- [ ] Feedback submission endpoint publishes event to Redis after DB commit
- [ ] Event payload includes: application_id, feedback_id, interviewer_id, technical_score, communication_score, recommendation, timestamp
- [ ] Event published within 50ms of DB commit (non-blocking)
- [ ] Feedback edits also trigger events (if feedback updated later)
- [ ] Failed event publishing doesn't block feedback submission (graceful)
- [ ] Unit tests verify event structure
- [ ] Integration test verifies recruiter sees feedback appear in real-time

**Validation steps:**
1. Submit feedback via API → verify event in Redis
2. Edit existing feedback → verify updated event published
3. Verify only authorized users see feedback event (privacy check)

---

### 3. 🚨 Priority
🔴 High — Supports real-time feedback visibility (AC #2)

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 2
- **Estimated Time:** 4–6 hours

---

### 5. 👤 Assignment
- **Team/Role:** Backend Engineer (Interview/Feedback Service Owner)
- **Suggested Assignee:** Backend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Backend / API
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Ensure feedback scores are validated before event publication
- Consider notification throttling if multiple feedback submissions occur simultaneously

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #4 (Redis Pub/Sub), #3 (Event Schema)
- **External Docs/Designs:** Interview/Feedback Service code (TBD)

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #7: Implement Frontend WebSocket Connection & Subscription

### 1. 📋 Description
**Purpose:** Establish WebSocket client connection on the frontend that subscribes to real-time events for the current job/dashboard. Handle connection lifecycle (connect, disconnect, reconnect).

**Details:**
- Create React hook: `useWebSocket()` that manages connection state
- Connect to WebSocket server on component mount with JWT token
- Subscribe to job-specific channel (e.g., `job_123:updates`) based on current context
- Implement automatic reconnection with exponential backoff (1s, 2s, 4s, 8s, max 30s)
- Detect network disconnection and set "offline" state in UI
- Implement heartbeat/pong response to keep connection alive
- Clean up connection on component unmount
- Expose connection status as React context (`useWebSocketStatus()`)

---

### 2. ✅ Acceptance Criteria
- [ ] `useWebSocket()` hook establishes connection on mount with JWT token
- [ ] Successfully subscribes to job channel within 500ms
- [ ] Connection status available via React context (connected, connecting, disconnected)
- [ ] Automatic reconnection triggers on connection loss with exponential backoff
- [ ] Heartbeat responds to server ping every 30 seconds
- [ ] No memory leaks (connections properly cleaned up on unmount)
- [ ] Works with browser DevTools WebSocket inspector (debuggable)
- [ ] Unit tested with mock WebSocket server

**Validation steps:**
1. Load dashboard → verify WebSocket connection established and job channel subscribed
2. Disconnect WebSocket → verify UI shows "offline" badge
3. Reconnect network → verify automatic reconnection within 5 seconds
4. Leave page → verify connection cleaned up (no lingering connections in DevTools)

---

### 3. 🚨 Priority
🔴 High — Required for all real-time updates

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 3
- **Estimated Time:** 1 day

---

### 5. 👤 Assignment
- **Team/Role:** Frontend Engineer (React/TypeScript)
- **Suggested Assignee:** Frontend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Frontend / UI
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use Socket.io client library for easier reconnection management
- Implement proper TypeScript types for events
- Consider storing connection URL in environment config

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #2 (WebSocket Server), #8 (State Update Handler), #9 (UI Components)
- **External Docs/Designs:** Socket.io client library, React hooks pattern

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #8: Implement Real-Time State Update Handler (Frontend)

### 1. 📋 Description
**Purpose:** Process incoming WebSocket events on the frontend and update React state/UI in real-time. This handles the core logic of "when event arrives, update dashboard".

**Details:**
- Create event handler for `status:updated` events → update application status in state
- Create event handler for `feedback:submitted` events → add feedback to candidate profile
- Create event handler for `presence:changed` events → update "who is viewing" indicator
- Implement optimistic UI updates (update UI immediately, sync with server in background)
- Handle duplicate events (idempotency keys)
- Implement state reconciliation on reconnection (fetch full state from server)
- Ensure UI updates don't cause unnecessary re-renders (memoization, selectors)
- Implement error handling: invalid event → log but don't crash

---

### 2. ✅ Acceptance Criteria
- [ ] Event listeners registered for all event types in event schema
- [ ] Status updates appear in UI within 1 second of event arrival
- [ ] Feedback updates appear instantly (UI shows "Feedback from [Name] just now")
- [ ] Presence updates show who is currently viewing candidate
- [ ] Duplicate events (same event_id) handled correctly (no duplicates in UI)
- [ ] Network reconnection triggers state sync (fetch latest state from server)
- [ ] Invalid events logged to console but don't crash app
- [ ] UI updates memoized to prevent unnecessary re-renders

**Validation steps:**
1. Send status update event → verify candidate card updates within 1s
2. Send duplicate event → verify only one UI update
3. Disconnect and reconnect → verify state is current after reconnect
4. Open React DevTools → verify no unnecessary component re-renders

---

### 3. 🚨 Priority
🔴 High — Core real-time update logic

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 5
- **Estimated Time:** 1.5 days

---

### 5. 👤 Assignment
- **Team/Role:** Frontend Engineer (React/State Management)
- **Suggested Assignee:** Frontend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Frontend / State Management
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Consider using Redux middleware or Zustand actions for event handling
- Implement state diff calculation to minimize re-renders
- Add feature flag to disable real-time updates for testing

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #7 (WebSocket Connection), #9 (UI Components), #3 (Event Schema)
- **External Docs/Designs:** Redux middleware pattern, React context API

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #9: Build Real-Time Status Update UI Components

### 1. 📋 Description
**Purpose:** Create React components that render candidate status updates in real-time, including visual indicators, animations, and notification badges.

**Details:**
- Build `CandidateCard` component that re-renders when status changes
- Implement status animation: fade-in/pulse effect when status updates
- Build notification badge (blue dot) on updated candidates
- Implement "Last updated X seconds ago" timestamp
- Build "Online now" presence indicator showing who else is viewing
- Implement mobile-responsive layout (desktop 1920px → mobile 375px)
- Add loading skeleton while real-time state syncs after reconnection
- Ensure accessibility: ARIA labels, keyboard navigation

---

### 2. ✅ Acceptance Criteria
- [ ] `CandidateCard` component renders status with correct icon and color
- [ ] Status update animation smooth (no flickering) and accessible
- [ ] Notification badge appears on card when status changes
- [ ] "Last updated X seconds ago" timestamp updates every second
- [ ] "Online now" indicator shows avatars of other users viewing
- [ ] Mobile view: all elements visible at 375px width (no horizontal scroll)
- [ ] Accessibility audit: WCAG AA pass (keyboard nav, screen reader support)
- [ ] Component unit tested with @testing-library/react

**Validation steps:**
1. Render component → verify all elements visible and styled correctly
2. Simulate status change event → verify animation plays smoothly
3. Test on mobile (375px) → verify responsive layout works
4. Screen reader test → verify all content accessible
5. Keyboard navigation → verify all interactive elements reachable via Tab

---

### 3. 🚨 Priority
🔴 High — User-facing component for UX

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 3
- **Estimated Time:** 1 day

---

### 5. 👤 Assignment
- **Team/Role:** Frontend Engineer (React/Component Library)
- **Suggested Assignee:** Frontend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Frontend / UI Components
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use design tokens from Ticket #1 Figma file
- Implement animation with CSS modules or Framer Motion for smoothness
- Consider Storybook for component documentation and testing

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #1 (Design), #8 (State Update Handler)
- **External Docs/Designs:** Figma mockups from Ticket #1, React component patterns

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #10: Implement Browser Tab Notification Badge

### 1. 📋 Description
**Purpose:** Update the browser tab title with a notification badge (blue dot) when candidate status changes, even if the browser tab is not in focus. This addresses AC #3 (notification badge on browser tab).

**Details:**
- Update document.title to show badge indicator (e.g., "🔵 ATS - 1 new update")
- Detect when tab is not in focus using Page Visibility API
- Show badge count (e.g., "3 updates") if multiple updates occurred while tab unfocused
- Clear badge when user focuses tab (page visibility change)
- Handle edge case: many updates while tab unfocused (debounce to recent count)
- Use Favicon API to add small visual indicator (optional, browser support varies)

---

### 2. ✅ Acceptance Criteria
- [ ] Browser tab title updates with notification badge when status changes
- [ ] Badge persists while tab is out of focus
- [ ] Badge clears when tab regains focus
- [ ] If 3+ updates occur while tab unfocused, show "3+ new updates" or count
- [ ] Works across different browsers (Chrome, Firefox, Safari, Edge)
- [ ] Does not interfere with existing app title (resets to normal on page change)
- [ ] Tested with unit tests (mock Page Visibility API)

**Validation steps:**
1. Update candidate status while browser tab in background → verify badge appears in tab title
2. Click tab to focus → verify badge disappears
3. Multiple updates while unfocused → verify count shows correctly
4. Test on Chrome, Firefox, Safari → verify works cross-browser

---

### 3. 🚨 Priority
🟡 Medium — Important UX enhancement but not critical path

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 2
- **Estimated Time:** 2–3 hours

---

### 5. 👤 Assignment
- **Team/Role:** Frontend Engineer (React)
- **Suggested Assignee:** Frontend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Frontend / UI
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use React useEffect hook to manage tab visibility listener
- Debounce rapid status updates to prevent excessive title changes
- Consider favicon indicator for browsers that support it (Favico.js library)

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #8 (State Update Handler)
- **External Docs/Designs:** MDN Page Visibility API, Favico.js

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #11: Implement State Sync Endpoint (Backend)

### 1. 📋 Description
**Purpose:** Create a REST API endpoint that returns the current state of all candidates for a job. This is used by the frontend to sync state after reconnecting (AC #4).

**Details:**
- Endpoint: `GET /api/jobs/{job_id}/applications/current-state`
- Response includes: all applications with current status, latest feedback, presence info
- Request should be authenticated (JWT token)
- Response should be paginated (limit: 100 by default)
- Include timestamp of last state update (for conflict resolution)
- Cache response in Redis (5-minute TTL) to reduce DB queries
- Return only fields that changed since last sync (delta sync is optional, full sync is minimum)

---

### 2. ✅ Acceptance Criteria
- [ ] Endpoint returns all applications for job with current status
- [ ] Response includes: application_id, status, latest_feedback, updated_at timestamp
- [ ] Authentication required (JWT token verified)
- [ ] Response paginated with default limit: 100, max: 1000
- [ ] Response time < 500ms (using Redis cache)
- [ ] Tested with unit tests (mock DB, Redis)
- [ ] Load test: 1000 calls/sec → verify <500ms latency p99

**Validation steps:**
1. Call endpoint → verify all applications returned with current status
2. Call with pagination (page=2, limit=50) → verify correct subset returned
3. Call without auth token → verify 401 Unauthorized
4. Load test with concurrent requests → verify latency <500ms

---

### 3. 🚨 Priority
🔴 High — Required for reconnection sync

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 2
- **Estimated Time:** 3–4 hours

---

### 5. 👤 Assignment
- **Team/Role:** Backend Engineer (API)
- **Suggested Assignee:** Backend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Backend / API
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Implement Redis caching to reduce database load
- Document response schema in OpenAPI
- Consider adding `since` parameter to return only recent updates (delta sync for future optimization)

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #7 (Frontend WebSocket), #8 (State Update Handler)
- **External Docs/Designs:** REST API standards, Redis caching patterns

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #12: Implement Frontend Reconnection & State Sync Logic

### 1. 📋 Description
**Purpose:** Handle the reconnection scenario (AC #4): when the user regains internet connection, automatically sync the latest state from the server to ensure the dashboard shows current data.

**Details:**
- Detect network reconnection using `navigator.onLine` change event
- When reconnection detected, call state sync endpoint (#11) to fetch latest state
- Compare fetched state with local state → identify deltas
- Show loading indicator while sync in progress ("Syncing...")
- Handle conflict resolution (server state takes precedence)
- Log sync operation for debugging
- Hide loading indicator once sync complete
- Handle sync errors (retry up to 3 times, then show error banner)

---

### 2. ✅ Acceptance Criteria
- [ ] Network reconnection detected automatically (within 2 seconds)
- [ ] State sync endpoint called on reconnection
- [ ] Latest state from server merged into local state
- [ ] UI shows "Syncing..." indicator during state sync
- [ ] Sync completes and indicator disappears within 2 seconds
- [ ] Server state takes precedence in conflict resolution
- [ ] Sync errors retry 3 times automatically
- [ ] All sync operations logged with timestamp and result

**Validation steps:**
1. Go offline → go online → verify state syncs automatically
2. Make changes while offline → reconnect → verify latest server state shown (offline changes discarded or flagged)
3. Simulate sync endpoint error → verify retry logic works
4. Verify loading indicator visible during sync and disappears after

---

### 3. 🚨 Priority
🔴 High — Critical for offline/reconnection handling

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 3
- **Estimated Time:** 1 day

---

### 5. 👤 Assignment
- **Team/Role:** Frontend Engineer (React)
- **Suggested Assignee:** Frontend Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** Feature
- **Area:** Frontend / State Management
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Implement with React hooks for network status listening
- Consider persisting offline changes (advanced: optional for v1.1)
- Show user-friendly error message if sync fails after retries

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #7 (WebSocket Connection), #11 (State Sync Endpoint)
- **External Docs/Designs:** MDN Navigator.onLine, React useEffect patterns

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #13: Integration Testing - Real-Time Updates End-to-End

### 1. 📋 Description
**Purpose:** Create comprehensive integration tests that verify the entire real-time update flow: user action → backend event → Redis → WebSocket → frontend update.

**Details:**
- Test scenario 1: Update candidate status via API → verify event in Redis → verify WebSocket event received → verify UI updated
- Test scenario 2: Submit feedback → verify event published → verify appears in recruiter dashboard
- Test scenario 3: Multiple concurrent status updates → verify all updates appear in correct order
- Test scenario 4: Network disconnect/reconnect → verify state sync after reconnection
- Test scenario 5: Tab in background → verify notification badge appears
- Use test containers (Docker) to spin up Redis, WebSocket server, frontend test client
- Mock external dependencies (job board APIs, calendar APIs)

---

### 2. ✅ Acceptance Criteria
- [ ] Test scenario 1: Status update flow works end-to-end (API → Redis → WebSocket → UI)
- [ ] Test scenario 2: Feedback submission appears in real-time dashboard
- [ ] Test scenario 3: Concurrent updates processed in correct order
- [ ] Test scenario 4: Reconnection syncs state correctly
- [ ] Test scenario 5: Notification badge appears/disappears with focus
- [ ] All tests automated and run in CI/CD pipeline
- [ ] Tests run < 5 minutes total
- [ ] Coverage: all major user paths covered

**Validation steps:**
1. Run integration test suite → verify all tests pass
2. Simulate latency between services → verify tests still pass with 200ms+ delays
3. Run on multiple browsers (Selenium/Playwright) → verify cross-browser compatibility

---

### 3. 🚨 Priority
🔴 High — Critical quality gate before release

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 5
- **Estimated Time:** 1.5 days

---

### 5. 👤 Assignment
- **Team/Role:** QA Engineer / Test Automation Engineer
- **Suggested Assignee:** QA Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** QA / Testing
- **Area:** Testing / Quality Assurance
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use Playwright or Cypress for browser automation
- Use Docker Compose for test environment setup
- Implement test helpers for WebSocket event injection
- Generate test report with coverage metrics

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #2-12 (All implementation tickets)
- **External Docs/Designs:** Playwright documentation, Docker Compose

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #14: Performance Testing - Real-Time Latency Validation

### 1. 📋 Description
**Purpose:** Verify that real-time updates meet the <1 second latency requirement (AC #1). Measure end-to-end latency from user action to UI update.

**Details:**
- Load test: 100 concurrent users viewing same dashboard
- Measure latency: time from API call to UI update on client
- Measure WebSocket latency: event published → received by client
- Measure CPU/memory usage of WebSocket server under load
- Measure Redis throughput: events/sec and latency percentiles
- Identify bottlenecks (network, server, client rendering)
- Generate performance report with metrics and recommendations
- Establish performance baseline for regression testing

---

### 2. ✅ Acceptance Criteria
- [ ] End-to-end latency (API call → UI update): < 1000ms p50, < 2000ms p99
- [ ] WebSocket event latency (publish → receive): < 500ms p99
- [ ] WebSocket server CPU usage: < 50% with 100 concurrent connections
- [ ] WebSocket server memory usage: < 500MB with 100 concurrent connections
- [ ] Redis throughput: > 10,000 events/sec
- [ ] No memory leaks detected over 30-minute load test
- [ ] Performance report generated with graphs and analysis

**Validation steps:**
1. Run load test with 100 concurrent users → collect latency metrics
2. Identify top 3 bottlenecks from trace data
3. Verify all metrics within acceptable ranges
4. Document baseline metrics in team wiki

---

### 3. 🚨 Priority
🟡 Medium → High (depends on latency requirements strictness)

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 3
- **Estimated Time:** 1 day

---

### 5. 👤 Assignment
- **Team/Role:** QA / Performance Engineer
- **Suggested Assignee:** QA Engineer or DevOps Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** QA / Testing
- **Area:** Performance / Load Testing
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use tools like k6, JMeter, or Gatling for load testing
- Implement APM instrumentation (e.g., DataDog APM) for detailed tracing
- Create automated performance regression tests for CI/CD

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #2-12 (All implementation tickets)
- **External Docs/Designs:** k6 documentation, APM tools

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 🎫 Ticket #15: Implement WebSocket Server Production Deployment & Monitoring

### 1. 📋 Description
**Purpose:** Set up production infrastructure for the WebSocket server including load balancing, monitoring, alerting, and disaster recovery.

**Details:**
- Configure WebSocket server deployment (Kubernetes or ECS)
- Set up load balancer (ALB/NLB) for WebSocket traffic
- Implement health checks (every 10 seconds)
- Configure auto-scaling (min 2 instances, max 10 based on CPU/memory)
- Set up CloudWatch metrics: connections, latency, errors, throughput
- Set up alerts: connection failures, latency > 1s, memory > 80%
- Configure log aggregation (CloudWatch Logs or ELK)
- Set up disaster recovery: failover to standby region if primary fails
- Document runbook for on-call engineers (troubleshooting guide)

---

### 2. ✅ Acceptance Criteria
- [ ] WebSocket server deployed to production with 2+ instances
- [ ] Load balancer distributes connections evenly across instances
- [ ] Health checks passing for all instances
- [ ] CloudWatch dashboard shows real-time metrics (connections, latency, errors)
- [ ] Alerts configured and tested (paged to on-call engineer)
- [ ] Logs aggregated and searchable (connection events, errors)
- [ ] Auto-scaling tested (scale up/down with simulated load)
- [ ] Failover tested (standby region takes over if primary fails)
- [ ] Runbook documented and accessible to engineers

**Validation steps:**
1. Deploy to production → verify 2+ instances running
2. Trigger health check → verify passed
3. Simulate high load → verify auto-scaling activates
4. Trigger alert condition → verify PagerDuty notification sent
5. Simulate failure → verify failover to standby region

---

### 3. 🚨 Priority
🔴 High — Required before production launch

---

### 4. ⏱️ Effort Estimation
- **Story Points:** 5
- **Estimated Time:** 1.5 days

---

### 5. 👤 Assignment
- **Team/Role:** DevOps / Infrastructure Engineer
- **Suggested Assignee:** DevOps Engineer

---

### 6. 🏷️ Labels / Tags
- **Type:** DevOps / Infrastructure
- **Area:** DevOps / Infrastructure
- **Sprint/Version:** Sprint 1 / v1.0

---

### 7. 💬 Comments & Notes
- Use Infrastructure as Code (Terraform, CloudFormation) for reproducibility
- Document all deployment steps in runbook
- Ensure on-call team trained on escalation procedures

---

### 8. 🔗 Links & References
- **Parent User Story:** Recruiter Views Real-Time Candidate Status Updates
- **Related Tickets:** #2 (WebSocket Server)
- **External Docs/Designs:** Kubernetes / ECS documentation, Terraform examples

---

### 9. 📝 Change History
| Date | Change | Author |
|------|--------|--------|
| 2026-05-10 | Ticket created | Agile BA |

═══════════════════════════════════════════════════════════════════════════

---

## 📊 Ticket Summary

| # | Title | Role | Priority | Story Points |
|---|-------|------|----------|--------------|
| 1 | Design Real-Time Dashboard UI Mockups | UX Designer | 🔴 High | 2 |
| 2 | Implement WebSocket Server Infrastructure | Backend/DevOps | 🔴 High | 5 |
| 3 | Define WebSocket Event API & Message Schema | Backend Architect | 🔴 High | 2 |
| 4 | Implement Redis Pub/Sub for Event Distribution | Backend/Infrastructure | 🔴 High | 3 |
| 5 | Implement Application Status Change Event Publishing | Backend | 🔴 High | 3 |
| 6 | Implement Interview Feedback Event Publishing | Backend | 🔴 High | 2 |
| 7 | Implement Frontend WebSocket Connection & Subscription | Frontend | 🔴 High | 3 |
| 8 | Implement Real-Time State Update Handler (Frontend) | Frontend | 🔴 High | 5 |
| 9 | Build Real-Time Status Update UI Components | Frontend | 🔴 High | 3 |
| 10 | Implement Browser Tab Notification Badge | Frontend | 🟡 Medium | 2 |
| 11 | Implement State Sync Endpoint (Backend) | Backend | 🔴 High | 2 |
| 12 | Implement Frontend Reconnection & State Sync Logic | Frontend | 🔴 High | 3 |
| 13 | Integration Testing - Real-Time Updates End-to-End | QA | 🔴 High | 5 |
| 14 | Performance Testing - Real-Time Latency Validation | QA/DevOps | 🟡 Medium | 3 |
| 15 | Implement WebSocket Server Production Deployment & Monitoring | DevOps | 🔴 High | 5 |

---

## 📈 Summary Metrics

- **Total Story Points:** 50
- **Estimated Team Capacity:** ~2 weeks (for 6-person team @ 8.33 pts/person/week)
- **Estimated Time:** 10 business days (full-time team)
- **High Priority Tickets:** 13 / 15 (87%)
- **Teams Involved:** 5 (Design, Frontend, Backend, QA, DevOps)

---

## 🔄 Ticket Dependencies & Ordering

**Recommended Execution Order (by phase):**

### Phase 1: Planning & Design (Days 1-2)
- Ticket #1 (Design) - can start immediately
- Ticket #3 (API Schema) - can start immediately (parallel with #1)

### Phase 2: Infrastructure (Days 3-5)
- Ticket #2 (WebSocket Server) - depends on #3
- Ticket #4 (Redis Pub/Sub) - can start parallel with #2
- Ticket #11 (State Sync Endpoint) - can start after #3

### Phase 3: Backend Events (Days 6-8)
- Ticket #5 (Status Event Publishing) - depends on #2, #4
- Ticket #6 (Feedback Event Publishing) - depends on #2, #4

### Phase 4: Frontend (Days 9-12)
- Ticket #7 (WebSocket Connection) - depends on #2, #3
- Ticket #8 (State Update Handler) - depends on #7
- Ticket #9 (UI Components) - depends on #1, #8
- Ticket #10 (Tab Notification) - depends on #8
- Ticket #12 (Reconnection Logic) - depends on #7, #11

### Phase 5: Testing & Deployment (Days 13-15)
- Ticket #13 (Integration Tests) - depends on all implementation tickets
- Ticket #14 (Performance Tests) - depends on all implementation tickets
- Ticket #15 (Production Deployment) - depends on #13, #14

---

## 🚨 Risk & Mitigation

| Risk | Severity | Mitigation |
|------|----------|-----------|
| WebSocket latency > 1s under load | High | Performance testing early (Ticket #14); load test prototypes |
| State inconsistency between clients | High | Implement idempotency keys; conflict resolution strategy |
| Redis single point of failure | High | Implement Redis failover (cluster mode); backup strategy |
| Browser compatibility issues | Medium | Cross-browser testing (Ticket #13); feature detection |
| Mobile performance degradation | Medium | Mobile-specific load testing; optimize animations |

---

**End of Sprint Tickets Document**
