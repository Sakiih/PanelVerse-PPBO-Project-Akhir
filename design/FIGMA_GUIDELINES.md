# PanelVerse Design Reference Guidelines

## A. Design Overview

Images in `design/references/` are the project's primary visual references for PanelVerse. They record Shinigami interface examples; they do not grant rights to reuse the original brand or content. The `assets/` directory here holds supporting assets and comic content samples.

## B. Design Consistency

Implementations should follow the available reference for the relevant screen: layout, spacing, typography, color palette, background, component placement, navigation, and responsive behavior. Match only details that can be observed. Do not invent precise color values, font sizes, or spacing measurements where the screenshot does not establish them; document a reasonable implementation choice with Member 1 when a decision is needed. When a page has no reference, coordinate its visual direction with Member 1 and Member 2.

## C. Asset Usage

- `references/homepage/`: homepage captures, including search/profile overlays.
- `references/catalog/`: all-comics views and the search overlay. The overlay is shown over the homepage, but is useful to Member 3 for search behavior.
- `references/comic-detail/`: comic detail and chapter-list references. No source image was confidently identified as this view; this folder is intentionally absent until one is found.
- `references/reader/`: reserved for reader interface screenshots. The five originally presumed reader references were visually checked: `Damn Reincarnation 2 - Shinigami.png` is a homepage, and the four `The Extra’s Academy...` images are tall comic page content. They are not reader-interface screenshots. Existing copies under `references/reader/` predate this pass and are not authoritative; consult the manifest and do not use them as reader UI references.
- `references/library/`: Pustaka/library states.
- `references/notifications/`: notification popover and notifications page.
- `references/premium/`: premium page.
- `references/guide/`: guide page. One source is byte-identical to the other and is recorded as a duplicate in the manifest.
- `references/authentication/`: account settings screens. No login/register screen was identified; the folder contains account settings references, not authentication-form examples.
- `references/admin/`: reserved for admin references; no admin screen was identified.
- `assets/logo/`, `assets/icons/`, `assets/illustrations/`: reserved for independently usable assets of those types. No standalone source files of these types were identified, so these folders are omitted.
- `assets/images/comic-content/`: four supplied long comic-page images, kept separate from interface references. Use only where content samples are appropriate and permitted.
- Root `assets/` remains the untouched original source collection. Organized files are copies.

These are screenshots, not production assets. Rebuild the interface with Blade, HTML, CSS, JavaScript, and the stack specified in `MASTER_PROJECT.md`. Never use a screenshot as a page background or substitute for implemented UI.

## D. Member Design Assignment

- **Member 1:** inspect all references for analysis, consistency, review, and integration.
- **Member 2:** use all relevant references to establish the shared design foundation and reusable components.
- **Member 3:** use homepage, catalog, and search references only for its page scope.
- **Member 4:** use comic detail, chapter-list, and reader references when identified. The current reader folder has no verified reader UI reference; coordinate that gap rather than treating comic-page content as a UI screenshot.
- **Member 5:** database work; follow the general design contract without taking on frontend implementation.
- **Member 6:** backend and API work; follow the general design contract without taking on frontend implementation.
- **Member 7:** OOP and SOLID work; follow the general design contract without taking on frontend implementation.

## E. Implementation Rules

Recreate the visual structure using the project technologies. Screenshots serve as visual references only. Do not embed a screenshot as a background or use it instead of implementing the interface. Preserve supplied source files; ask Member 1 before any source asset is removed.
