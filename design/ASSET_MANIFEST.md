# PanelVerse Asset Manifest

Visual classification was based on inspecting the supplied images, not filenames alone. All files listed below remain unchanged in `assets/`; organized destinations are copies. Resolution is in pixels (width × height). “Identified” means the visible screen/content type is clear; it does not assert rights to reuse branded or comic content.

| Original Filename | New Filename | Category | Description | Resolution | Status | Members |
|---|---|---|---|---:|---|---|
| `Damn Reincarnation 2 - Shinigami.png` | `references/homepage/01-homepage-featured-catalog.png` | Homepage | Homepage capture with featured comic area and recommendation/cards; despite filename, not a reader. | 1536×1641 | Identified; filename misleading | 1, 2, 3 |
| `Shinigami.png` | `references/homepage/02-homepage-long-capture.png` | Homepage | Long homepage capture with hero carousel, ranked rows, comic cards, and footer. | 1536×2903 | Identified | 1, 2, 3 |
| `Shinigami-1.png` | `references/homepage/03-homepage-profile-menu.png` | Homepage | Homepage with account/profile dropdown open. | 1536×2903 | Identified | 1, 2, 3 |
| `Shinigami-2.png` | `references/notifications/01-notification-popover.png` | Notifications | Homepage with notification popover open. | 1536×2903 | Identified | 1, 2 |
| `Shinigami-3.png` | `references/catalog/01-search-overlay.png` | Catalog / Search | Homepage behind search dialog, including query field and trending results. | 1536×2903 | Identified | 1, 2, 3 |
| `Semua Komik - Shinigami.png` | `references/catalog/02-all-comics.png` | Catalog | Tall all-comics listing capture. | 1536×2328 | Identified | 1, 2, 3 |
| `Semua Komik - Shinigami-1.png` | `references/catalog/03-all-comics-variant.png` | Catalog | Alternate all-comics listing capture. | 1536×2835 | Identified | 1, 2, 3 |
| `Pustaka - Shinigami.png` | `references/library/01-library-empty-state.png` | Library | Pustaka/library view with empty-state message. | 1536×730 | Identified | 1, 2 |
| `Pustaka - Shinigami-1.png` | `references/library/02-library-state.png` | Library | Pustaka view with a saved comic entry. | 1536×730 | Identified | 1, 2 |
| `Pustaka - Shinigami-2.png` | `references/library/03-library-state.png` | Library | Alternate Pustaka state with no visible comic card. | 1536×730 | Identified | 1, 2 |
| `Pustaka - Shinigami-3.png` | `references/library/04-library-state.png` | Library | Pustaka view with a saved comic entry and another visible state. | 1536×730 | Identified | 1, 2 |
| `Notifikasi - Shinigami.png` | `references/notifications/02-notifications-page.png` | Notifications | Full notifications page/settings view. | 1536×1059 | Identified | 1, 2 |
| `Premium - Shinigami.png` | `references/premium/01-premium-page.png` | Premium | Premium subscription and plan comparison page. | 1536×2410 | Identified | 1, 2 |
| `Panduan - Shinigami.png` | `references/guide/01-guide.png` | Guide | Guide/help page capture. | 1536×2037 | Identified | 1, 2 |
| `Panduan - Shinigami-1.png` | `references/guide/02-guide-identical-duplicate.png` | Guide | Exact byte-for-byte duplicate of `Panduan - Shinigami.png`; retained as a separate copy for traceability. | 1536×2037 | Identified; exact duplicate (SHA-256 match) | 1, 2 |
| `Shinigami-4.png` | `references/authentication/01-account-settings-payment.png` | Account settings | Settings page with payment tab selected and premium status. | 1536×992 | Identified; not login/register | 1, 2 |
| `Shinigami-5.png` | `references/authentication/02-account-settings-reading-preferences.png` | Account settings | Reading preference settings with genre and theme choices. | 1536×1169 | Identified; not login/register | 1, 2 |
| `Shinigami-6.png` | `references/authentication/03-account-settings-notifications.png` | Account settings | Notification preference settings. | 1536×992 | Identified; not login/register | 1, 2 |
| `Shinigami-7.png` | `references/authentication/04-account-settings-profile.png` | Account settings | Profile/account settings form. | 1536×992 | Identified; not login/register | 1, 2 |
| `Shinigami-8.png` | `references/authentication/05-account-settings-profile-variant.png` | Account settings | Account/profile settings view with identity details. | 1536×992 | Identified; not login/register | 1, 2 |
| `The Extra’s Academy Survival Guide Chapter 133 - Shinigami.png` | `assets/images/comic-content/extra-academy-chapter-133-page-01.png` | Comic content | Very tall comic page image; content sample, not a UI screenshot. | 364×32768 | Identified; comic content | 4 |
| `The Extra’s Academy Survival Guide Chapter 133 - Shinigami-1.png` | `assets/images/comic-content/extra-academy-chapter-133-page-02.png` | Comic content | Very tall comic page image; content sample, not a UI screenshot. | 364×32768 | Identified; comic content | 4 |
| `The Extra’s Academy Survival Guide Chapter 133 - Shinigami-2.png` | `assets/images/comic-content/extra-academy-chapter-133-page-03.png` | Comic content | Very tall comic page image; content sample, not a UI screenshot. | 383×32768 | Identified; comic content | 4 |
| `The Extra’s Academy Survival Guide Chapter 133 - Shinigami-3.png` | `assets/images/comic-content/extra-academy-chapter-133-page-04.png` | Comic content | Very tall comic page image; content sample, not a UI screenshot. | 364×32768 | Identified; comic content | 4 |

## Classification notes

- **24** original files in `assets/` were visually reviewed and classified. None of those source images is marked `NEEDS_REVIEW`.
- The five filenames previously thought to be reader references were checked individually. `Damn Reincarnation 2 - Shinigami.png` is a homepage capture. The four `The Extra’s Academy...` images are comic-page content, not reader UI screenshots. There is currently **no verified reader UI screenshot** in the supplied source assets.
- No comic-detail/chapter-list UI, login/register form, admin dashboard, standalone logo, standalone icon, or standalone illustration was confidently identified. Those target folders are omitted until a real asset exists. Do not infer these views from account-setting or homepage screenshots.
- `Panduan - Shinigami.png` and `Panduan - Shinigami-1.png` have identical SHA-256 hashes. No other exact duplicate was found among the 24 originals.
- There are pre-existing copies in `references/reader/` from before this classification pass. They are legacy copies and are not authoritative: the filenames and categories should not be used to infer UI content. The authoritative mapping is the table above. Original files in root `assets/` and all pre-existing files have been preserved.
- Member mapping: 1 reviews/integrates all; 2 establishes shared foundation; 3 uses homepage/catalog/search; 4 uses detail/chapter/reader when verified; 5–7 follow the shared contract without visual implementation ownership.
