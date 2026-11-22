# Platform Research, Publishing and Account Safety

## Research policy

The competitive-research system must rely on legitimate, proportionate and reproducible signals:

- Public search results, public creator/channel pages and publicly visible content.
- Platform-native search, recommendations, comments and first-party analytics.
- Google Trends and search-result observations.
- Public community discussions, used to understand questions rather than harvest personal profiles.
- Official platform APIs where our account type, permissions and use case qualify.
- User-provided exports and our own account data.

Record the URL, observation date, query, metric shown, limitations and relevant learning. Do not treat views or search ranking as proof of topic demand, and do not infer private audience information.

## Instagram and social-platform guardrails

The reviewed repositories include bots and unofficial API wrappers that automate likes, follows, comments, DMs, private endpoints, session reuse or mass media downloads. Creator-OS will not use these as dependencies.

Explicitly excluded:
- InstaPy and GramAddict engagement automation.
- InstaTouch / instagram-scraper scraping of followers, likers, comments or session-protected feeds.
- instagrapi private mobile API, session IDs, challenge workarounds or automated DMs/uploads.
- InstaLooter and other bulk downloaders for reusing third-party media.
- Any proxy rotation, browser fingerprinting or rate-limit evasion intended to bypass platform restrictions.

These projects introduce account restriction, privacy, data provenance, copyright and platform-terms risk. The InstaPy README itself describes its creator's Meta ban; instagrapi warns that private-API automation is fragile and recommends official APIs for account-owned workflows.

## Approved distribution process

1. Prepare a platform-neutral clean master.
2. Generate separate title, caption, description, cover and subtitle files for each platform.
3. Run the publishing auditor and rights/privacy checks.
4. Human approves the final content and publishing destination.
5. Publish using the platform's native creator tools or a permitted official API.
6. Save the canonical post URL, publish time and content ID.
7. Collect first-party analytics through native dashboards or authorised exports.
8. Update the analytics record and research backlog.

Do not automate posting until the target platform's current API terms, permissions, account eligibility, rate limits and data-retention obligations have been verified. Publishing remains human-approved.

## Human-in-the-loop publishing pattern

The LangChain Social Media Agent demonstrates a useful pattern: source URL → draft generation → inbox review → human edit/accept/reject → authorised publishing. Creator-OS will use this approval pattern without importing its Anthropic, Firecrawl, Arcade, LangSmith or Supabase dependency stack.

A publishing package must not be scheduled or posted simply because a model generated it. No AI agent may independently follow, like, comment, message or interact with other accounts on our behalf.

## Copyright and source handling

- A public post or video is not automatically reusable.
- Use creator content to understand market positioning and questions; do not download and republish the media.
- Keep original source links and short factual notes, not full copied transcripts.
- Use our own wording, examples, diagrams, screen recordings and licensed visual assets.
- Preserve attribution and licence notices for any asset we are authorised to reuse.
- Mark uncertain rights as blocked until resolved.

## Data minimisation

- Do not store Instagram passwords, session cookies, session IDs or private messages in Creator-OS.
- Do not collect follower lists, likers or personal profile data for competitive research.
- Store only aggregate public observations required for editorial decisions.
- Keep account tokens in the platform's approved secret store, never in Git, notebooks or content briefs.
