# Launch Reference

The launch gets attention once. Build for retention from day one.

---

## Pre-launch deploy checklist

Run every item before sharing any public URL.

### Security
- [ ] No secrets in version control (`gitleaks scan` passes clean)
- [ ] Environment variables set in production (not hardcoded)
- [ ] Rate limiting on: sign up, sign in, password reset, request creation
- [ ] Input validation on all user-submitted fields
- [ ] File upload restrictions: type whitelist, size limit, virus scan on verification docs
- [ ] `Content-Security-Policy` header set
- [ ] User-generated content not indexed by search engines (`robots.txt`, `noindex` meta)

### Infrastructure
- [ ] Database backups automated (daily minimum, test a restore)
- [ ] Error tracking live — Sentry receives a test error
- [ ] Uptime monitoring live — Uptime Kuma pings the API
- [ ] Deploy pipeline runs clean from a fresh repo clone
- [ ] Rollback procedure documented and tested

### Product
- [ ] Core loop completed end-to-end by a real person in production
- [ ] Email delivery tested (verification, notifications, password reset)
- [ ] Push notifications received on a real device
- [ ] App Store / Play Store build tested on a real device (not simulator)
- [ ] Privacy policy and terms of service live and linked from sign-up
- [ ] Account deletion works and is accessible from settings

### Legal (not legal advice — get a real review before launch)
- [ ] Privacy policy covers: what data is collected, how it's stored, how to delete it
- [ ] Terms cover: platform is not responsible for traveler conduct or safety
- [ ] Age restriction enforced if product involves strangers meeting in person
- [ ] GDPR / local data law compliance reviewed if launching in EU or India

---

## Soft launch (before public)

Do this before any public announcement:

1. **5 handpicked users** — people who fit the exact user profile, recruited personally
2. **Watch them use the product** — not a demo, you observe them navigate it cold
3. **Complete the core loop** — every one of them must finish the loop, not just sign up
4. **Fix what breaks** — ship fixes before moving to public launch

If fewer than 3 of 5 complete the loop: don't launch publicly yet.

---

## Day 1 launch sequence

**T-1 week:**
- Schedule posts in all channels for launch day
- Brief anyone helping with launch (co-founders, advisors, community contacts)
- Prepare 3 response templates for: "how does this work?", "is this safe?", "when is [feature] coming?"

**T-0 (launch day):**
- 8am: Post in all communities simultaneously
- 9am: Monitor for sign-ups and first loops — watch Sentry and PostHog live
- All day: Reply personally to every comment, DM, and review
- End of day: Post a public update on what happened ("We launched today, here's what we learned")

**T+1 to T+7:**
- DM every user who signed up but didn't complete the loop — ask why
- DM every user who completed the loop — ask what they'd tell a friend about it
- Ship at least one fix from user feedback before day 7

---

## What to measure in the first 7 days

| Metric | Healthy | Concerning |
|--------|---------|------------|
| Sign-up → loop started | >40% | <20% |
| Loop started → loop completed | >60% | <30% |
| Day 1 retention | >40% | <20% |
| Day 7 retention | >25% | <10% |
| Safety reports | 0 | Any |
| Sentry error rate | <1% of sessions | >5% |

Do not optimize for sign-up count. One user who completes the loop is worth 100 who sign up and leave.

---

## App store submission checklist

### iOS (App Store)
- [ ] Apple Developer account ($99/yr — no free alternative)
- [ ] App screenshots for all required device sizes
- [ ] App privacy nutrition label complete
- [ ] In-app purchase configured if any (even free tier)
- [ ] TestFlight tested on 10+ real devices
- [ ] Review notes prepared for Apple (explain verification flow)
- [ ] Fastlane `deliver` configured for automated submission

### Android (Play Store)
- [ ] Google Play Developer account ($25 one-time)
- [ ] Data safety section complete
- [ ] Signed release APK/AAB built via CI
- [ ] Internal test track → closed test → open test → production
- [ ] Fastlane `supply` configured for automated submission

**Realistic review times:**
- App Store: 1–3 days for first submission, same-day for updates
- Play Store: hours for first submission, minutes for updates
