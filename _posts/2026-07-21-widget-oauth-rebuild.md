---
layout: post
title: "Widget, OAuth, Rename"
date: 2026-07-21 23:30:00 -0700
categories: journal nightly
---

![July 21 Night](/assets/2026-07-21-night.svg)

## Tuesday (nightly wrap)

Fixed a systemic Mac widget bug across Talli and Epiphany: both were missing NSExtensionPointIdentifier in the widget's Info.plist, causing ITMS-90348 upload validation errors on App Store Connect. Added the missing key, re-archived both, and re-uploaded cleanly (talli commit 3feb0a4, epiphany commit 55f8665). Widget data sharing now works as intended on both platforms.

Wired Twitter/X OAuth keys into Epiphany on Vercel after re-activating the X developer account. Sign-in was previously disabled; now live in production. Tested end-to-end and committed the configuration.

Spine got renamed from "Spineless" to "Bindwise" after discovering "Spine" was already taken on the App Store. Icon export bug was also fixed (stale signing profile + missing UISupportedInterfaceOrientations in the project config), cleaned up in commit 531d730.

Healstack shipped v1.0 to App Store review. Medical device declaration was cleared via the asc web CLI—a regulated-category gate that has no programmatic path and requires manual dashboard interaction. The build is now in review (commit efbb929).

Lexly confirmed already merged: iOS and macOS are now a single universal app record after the xcodegen consolidation completed earlier (commit 67da0ac verified the cross-platform status). No code changes needed for the merge—just verification that it was already done.

Nullfolio (Portfolio iOS app) confirmed already submitted WAITING_FOR_REVIEW after the icon fix landed last session. The submission happened earlier; just needed status confirmation from ASC (commit 4e13221 logged the status grid).

Scoped a comprehensive Vercel to Cloudflare Pages migration plan (approved, saved to ~/.claude/plans/bright-baking-lake.md). 13–17 sessions planned; deferred for next session once usage headroom opens up. Roadmap logged the approval (commit 21f7a35).

Echo Mac and iOS both submitted for review tonight (v1.3.3) with bundle ID merge completed, metadata synced, and builds uploaded. Universal Purchase now live under the iOS app record (commits 3951f73 + acdceb8).

Litigate iOS resubmitted as v1.0.1 build 4 with name fix, support URL, and account deletion feature (commit 2e6690e). App Review blockers remain on the macOS side (app record doesn't exist yet—needs creation, not re-ship).

## Apps Summary

**Shipped tonight:** Healstack v1.0 (submitted for review, medical device declaration cleared via ASC web CLI). Epiphany Mac widget fix re-uploaded. Talli Mac widget fix re-uploaded. Echo Mac 1.3.3 submitted. Echo iOS 1.3.3 submitted (build 9). Litigate iOS 1.0.1 resubmitted.

**In flight:** Healstack (waiting review after medical device cleared). Echo (Mac + iOS 1.3.3 submitted 2026-07-21). Litigate iOS (1.0.1 resubmitted 2026-07-21, macOS still awaits app record creation). Inkpress iOS (1.0.2 waiting review, availability pending). Lexly iOS/Mac (1.1.1 in review after merge). Talli (3.5.6 submitted, Mac widget re-uploaded). Nullfolio iOS (submitted, waiting review).

**Active:** Epiphany (Twitter OAuth live after account reactivation). Spine renamed to Bindwise (icon export bug fixed). Cloudflare migration plan approved and staged for next session (bright-baking-lake.md).

**Blockers:** Healstack—regulated medical device declaration requires ASC dashboard (no API path). Epiphany—SnapTrade phantom holdings (disabled Trade tab, needs manual disconnect/reconnect in Settings); Twitter OAuth keys now wired but requires user dev-account setup. Litigate—macOS app record needs creation before iOS/macOS merge completes. Sparkjar—bundle ID rename (com.heyitsmejosh.spark → sparkjar) still pending. Echo—Mac screenshots deferred.
