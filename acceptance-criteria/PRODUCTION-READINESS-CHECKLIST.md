# Production Readiness Checklist
**Project:** Industrial Computer Vision Monitoring System  
**Version:** 1.0  
**Sign-off Required:** QA Lead + Project Owner  

---

> ⚠️ The system is NOT Production Ready until every Critical item is checked.

---

## 1. Functional Acceptance

- [ ] All required cameras integrated and online
- [ ] All AI use cases validated on production cameras
- [ ] Detection accuracy meets project-defined targets (post-PoC)
- [ ] Tracking ID persistence verified across frames
- [ ] Zone ENTER/EXIT events fire correctly
- [ ] Line crossing events fire with correct direction
- [ ] Occupancy calculation correct (current / max / min / avg)
- [ ] Queue count and threshold events correct
- [ ] Dwell time calculated correctly per track ID
- [ ] All event types generate with complete schema
- [ ] Alert system delivers: dashboard, webhook (as configured)
- [ ] CAMERA_OFFLINE event generated on disconnect
- [ ] STREAM_ERROR event generated on RTSP failure

## 2. API Acceptance

- [ ] All endpoints return correct response schemas
- [ ] Authentication enforced on all endpoints (401 without token)
- [ ] Authorization enforced per role (403 for unauthorized roles)
- [ ] Pagination working on list endpoints
- [ ] Filtering working (by camera_id, type, date range)
- [ ] Sorting working
- [ ] Rate limiting enforced (429 on exceed)
- [ ] API versioning active (/api/v1)
- [ ] Error responses have consistent schema
- [ ] RTSP credentials absent from all API responses

## 3. Dashboard Acceptance

- [ ] Overview shows correct camera counts (online/offline)
- [ ] Camera status list accurate in real time
- [ ] Events table shows all required columns
- [ ] Analytics charts render correctly
- [ ] Reports filterable by date range
- [ ] Dashboard inaccessible without authentication
- [ ] Live view functional

## 4. Security Acceptance

- [ ] No hardcoded secrets in source code (grep verified)
- [ ] No credentials in log files (grep verified)
- [ ] HTTPS enforced — HTTP rejected or redirected
- [ ] TLS 1.2+ only (1.0/1.1 disabled)
- [ ] Passwords stored as hashes (no plaintext in DB)
- [ ] JWT expiry enforced
- [ ] RBAC verified for all 4 roles
- [ ] SQL injection protection verified
- [ ] XSS protection verified
- [ ] IDOR protection verified
- [ ] Audit logs active (login, config changes, user changes)
- [ ] Security review / penetration test completed

## 5. Performance Acceptance

- [ ] 80-camera load test passed (no crashes, no event loss)
- [ ] Inference latency within PoC-defined target
- [ ] End-to-end event latency within PoC-defined target
- [ ] API response time within PoC-defined target
- [ ] GPU utilization has operational headroom (not at 100%)
- [ ] VRAM within safe limit
- [ ] No dropped frames under normal load
- [ ] Stress test (90-120 cameras) completed — graceful degradation confirmed

## 6. Reliability Acceptance

- [ ] RTSP auto-reconnect verified (single camera)
- [ ] RTSP auto-reconnect verified (multiple cameras simultaneously)
- [ ] One camera failure does NOT affect other cameras
- [ ] Frozen stream detection working
- [ ] AI service crash → auto-restart verified
- [ ] Backend crash → auto-restart verified
- [ ] Database unavailable (5 min) → recovery verified
- [ ] Full machine restart → all services auto-restart
- [ ] GPU OOM → graceful error, no data corruption
- [ ] Disk full → CRITICAL log, no silent event loss

## 7. Soak Testing Acceptance

- [ ] 8-hour soak test passed
- [ ] 24-hour soak test passed
- [ ] 72-hour soak test passed
- [ ] No memory leaks observed during soak
- [ ] No VRAM leaks observed during soak
- [ ] FPS stable throughout (within ±15% of baseline)
- [ ] No growing queue depth
- [ ] Zero event loss for verifiable events

## 8. Operational Acceptance

- [ ] Monitoring dashboards operational (GPU, CPU, RAM, camera health)
- [ ] Alerts configured and tested
- [ ] Structured logging active with correct fields
- [ ] Log rotation configured (disk won't fill)
- [ ] Backup procedure tested with successful restore
- [ ] Disaster recovery: RPO/RTO defined and tested
- [ ] Operations runbook completed
- [ ] All configuration in version control (except secrets)
- [ ] Model version, dataset version, config version all documented

---

## Sign-Off

| Role | Name | Signature | Date |
|---|---|---|---|
| QA Lead | | | |
| Project Owner | | | |
| Tech Lead | | | |

---

**Checklist Version:** 1.0  
**Next Review:** After every major release
