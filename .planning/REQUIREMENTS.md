# Requirements: Claude WordPress Skills Build-Out

**Defined:** 2026-02-06
**Core Value:** Every WordPress developer using Claude Code gets comprehensive, expert-level code review and development guidance across all major WordPress domains.

## v1 Requirements

Requirements for building out all 5 missing skills. Each maps to roadmap phases.

### Security Review (wp-security-review)

- [ ] **SEC-01**: SKILL.md with YAML frontmatter (name, description with trigger phrases, max 1024 chars)
- [ ] **SEC-02**: SQL injection detection — flag missing $wpdb->prepare(), raw query interpolation
- [ ] **SEC-03**: XSS prevention — detect missing esc_html(), esc_attr(), esc_url() on output
- [ ] **SEC-04**: CSRF/nonce verification — check wp_verify_nonce() in forms and AJAX handlers
- [ ] **SEC-05**: Input sanitization — detect missing sanitize_text_field(), sanitize_email(), etc.
- [ ] **SEC-06**: Output escaping — validate esc_*() function usage at display
- [ ] **SEC-07**: Capability checks — check current_user_can() before privileged operations
- [ ] **SEC-08**: Authentication validation — detect missing is_user_logged_in(), role checks
- [ ] **SEC-09**: REST API permission callbacks — ensure permission_callback on register_rest_route()
- [ ] **SEC-10**: File upload validation — check wp_handle_upload(), MIME types, extensions
- [ ] **SEC-11**: Direct file access prevention — ABSPATH checks in plugin/theme files
- [ ] **SEC-12**: Privilege escalation detection — missing caps in AJAX/REST, role manipulation
- [ ] **SEC-13**: Dangerous function detection — flag eval(), base64_decode(), unserialize(), exec(), shell_exec()
- [ ] **SEC-14**: Nonce context validation — verify nonce action/name matches operation
- [ ] **SEC-15**: WordPress-specific anti-patterns — serialize() without unserialize() protection, custom auth
- [ ] **SEC-16**: AJAX security patterns — wp_ajax_ vs wp_ajax_nopriv_ hooks, nonce in POST and GET
- [ ] **SEC-17**: Object injection prevention — unsafe unserialize() with user input
- [ ] **SEC-18**: wp_kses() vs wp_kses_post() — correct usage for context
- [ ] **SEC-19**: Security constants check — DISALLOW_FILE_EDIT, FORCE_SSL_ADMIN recommendations
- [ ] **SEC-20**: Search patterns for quick detection (grep commands for fast triage)
- [ ] **SEC-21**: Code examples following WordPress PHP Coding Standards (❌ BAD / ✅ GOOD pattern)
- [ ] **SEC-22**: Severity levels (CRITICAL/WARNING/INFO) applied consistently
- [ ] **SEC-23**: Output format matching wp-performance-review structure
- [ ] **SEC-24**: Common mistakes section (false positive scenarios to avoid)
- [ ] **SEC-25**: Reference doc — vulnerability patterns catalog
- [ ] **SEC-26**: Reference doc — escaping and sanitization guide
- [ ] **SEC-27**: Reference doc — authentication and authorization patterns
- [ ] **SEC-28**: Slash command /wp-sec-review (full review)
- [ ] **SEC-29**: Slash command /wp-sec (quick scan)

### Gutenberg Blocks (wp-gutenberg-blocks)

- [ ] **BLK-01**: SKILL.md with YAML frontmatter (name, description with trigger phrases)
- [ ] **BLK-02**: block.json validation — name, title, apiVersion, structure checks
- [ ] **BLK-03**: Render patterns — dynamic vs static block guidance
- [ ] **BLK-04**: InnerBlocks usage — InnerBlocks.Content in save, allowedBlocks, template
- [ ] **BLK-05**: useBlockProps() hook — required in edit and save functions
- [ ] **BLK-06**: Attribute schema — types, defaults, sources validation
- [ ] **BLK-07**: Edit vs save function consistency
- [ ] **BLK-08**: Block supports — color, spacing, typography in block.json
- [ ] **BLK-09**: Block deprecation — migration patterns when save changes
- [ ] **BLK-10**: Script/style enqueuing — editorScript, script, style paths in block.json
- [ ] **BLK-11**: Server-side rendering — render callback or render property
- [ ] **BLK-12**: Interactivity API patterns — data-wp-* directives, store, state management
- [ ] **BLK-13**: Block variations vs patterns — guidance on when to use which
- [ ] **BLK-14**: InnerBlocks.Content gotcha — dynamic blocks must still save InnerBlocks to DB
- [ ] **BLK-15**: useInnerBlocksProps hook order — useBlockProps before useInnerBlocksProps
- [ ] **BLK-16**: Block context — providesContext/usesContext for parent-child data flow
- [ ] **BLK-17**: Block Bindings API — dynamic attribute connections
- [ ] **BLK-18**: Block patterns registration — structure, categories, keywords
- [ ] **BLK-19**: Block hooks — blockHooks property for auto-insertion
- [ ] **BLK-20**: Custom block controls — InspectorControls, BlockControls integration
- [ ] **BLK-21**: wp_kses_post() with InnerBlocks warning — performance anti-pattern
- [ ] **BLK-22**: Search patterns for quick detection (grep commands)
- [ ] **BLK-23**: Code examples (PHP + React/JSX) following WordPress coding standards
- [ ] **BLK-24**: Severity levels and output format matching existing skill
- [ ] **BLK-25**: Common mistakes section
- [ ] **BLK-26**: Reference doc — block.json and block API guide
- [ ] **BLK-27**: Reference doc — React/JSX patterns for Gutenberg
- [ ] **BLK-28**: Reference doc — Interactivity API guide
- [ ] **BLK-29**: Slash command /wp-block-review (full review)
- [ ] **BLK-30**: Slash command /wp-block (quick scan)

### Theme Development (wp-theme-development)

- [ ] **THM-01**: SKILL.md with YAML frontmatter (name, description with trigger phrases)
- [ ] **THM-02**: theme.json structure validation — version, settings, styles, patterns
- [ ] **THM-03**: Template hierarchy — proper file naming for block and classic themes
- [ ] **THM-04**: Template parts — header.html, footer.html in block themes
- [ ] **THM-05**: FSE templates — templates directory structure, block markup
- [ ] **THM-06**: Conditional tags — is_front_page(), is_singular(), is_page() usage
- [ ] **THM-07**: get_template_part() — classic theme organization
- [ ] **THM-08**: Theme supports — add_theme_support() calls validation
- [ ] **THM-09**: Navigation menus — register_nav_menus() for classic, Navigation block for FSE
- [ ] **THM-10**: Global styles — color palettes, typography, spacing scales in theme.json
- [ ] **THM-11**: Block patterns — patterns directory, registration
- [ ] **THM-12**: Block theme vs classic theme detection — auto-detect and guide accordingly
- [ ] **THM-13**: theme.json version differences — v2 vs v3 features
- [ ] **THM-14**: Hardcoded styles anti-pattern — inline styles, style tags detection
- [ ] **THM-15**: Block stylesheets pattern — separate CSS for conditional loading
- [ ] **THM-16**: Child theme safety — parent theme function override checks
- [ ] **THM-17**: Custom templates registration — block theme templates/ naming
- [ ] **THM-18**: Template part areas — header, footer, sidebar areas
- [ ] **THM-19**: Style variations — styles/ directory structure validation
- [ ] **THM-20**: Root padding aware alignments — useRootPaddingAwareAlignments
- [ ] **THM-21**: Search patterns for quick detection (grep commands)
- [ ] **THM-22**: Code examples (PHP + HTML templates) following WordPress coding standards
- [ ] **THM-23**: Severity levels and output format matching existing skill
- [ ] **THM-24**: Common mistakes section
- [ ] **THM-25**: Reference doc — theme.json guide
- [ ] **THM-26**: Reference doc — template patterns (classic + FSE)
- [ ] **THM-27**: Reference doc — classic-to-block migration guide
- [ ] **THM-28**: Slash command /wp-theme-review (full review)
- [ ] **THM-29**: Slash command /wp-theme (quick scan)

### Plugin Development (wp-plugin-development)

- [ ] **PLG-01**: SKILL.md with YAML frontmatter (name, description with trigger phrases)
- [ ] **PLG-02**: Plugin header validation — required fields (name, version, author, etc.)
- [ ] **PLG-03**: Prefix convention — 4-5 char unique prefix on functions/classes
- [ ] **PLG-04**: Activation/deactivation hooks — register_activation_hook(), register_deactivation_hook()
- [ ] **PLG-05**: Uninstall cleanup — uninstall.php or register_uninstall_hook()
- [ ] **PLG-06**: Custom post types — register_post_type() parameters review
- [ ] **PLG-07**: Custom taxonomies — register_taxonomy() implementation
- [ ] **PLG-08**: Settings API usage — register_setting(), sections, fields
- [ ] **PLG-09**: Options API — get_option(), update_option(), delete_option() usage
- [ ] **PLG-10**: Hooks (actions/filters) — proper usage, priority, accepted args
- [ ] **PLG-11**: Internationalization — text domain, __(), _e(), esc_html__(), load_plugin_textdomain()
- [ ] **PLG-12**: Plugin Check standards — WordPress.org submission compliance patterns
- [ ] **PLG-13**: REST API endpoint registration — register_rest_route(), permission_callback
- [ ] **PLG-14**: AJAX handler patterns — wp_ajax_ and wp_ajax_nopriv_ hooks
- [ ] **PLG-15**: Admin menu registration — add_menu_page(), add_submenu_page() with capabilities
- [ ] **PLG-16**: Custom database tables — $wpdb->prefix, table creation in activation
- [ ] **PLG-17**: Cron job registration — wp_schedule_event(), schedule checks
- [ ] **PLG-18**: Transients API — set_transient() with proper expiration
- [ ] **PLG-19**: Function/class existence checks — function_exists(), class_exists()
- [ ] **PLG-20**: Conditional loading — is_admin() to separate admin/public code
- [ ] **PLG-21**: Search patterns for quick detection (grep commands)
- [ ] **PLG-22**: Code examples following WordPress PHP Coding Standards
- [ ] **PLG-23**: Severity levels and output format matching existing skill
- [ ] **PLG-24**: Common mistakes section
- [ ] **PLG-25**: Reference doc — plugin architecture patterns
- [ ] **PLG-26**: Reference doc — hooks and API guide
- [ ] **PLG-27**: Reference doc — WordPress.org submission checklist
- [ ] **PLG-28**: Slash command /wp-plugin-review (full review)
- [ ] **PLG-29**: Slash command /wp-plugin (quick scan)

### WooCommerce Development (wp-woocommerce-dev)

- [ ] **WOO-01**: SKILL.md with YAML frontmatter (name, description with trigger phrases)
- [ ] **WOO-02**: Custom product types — register_product_type(), product data stores
- [ ] **WOO-03**: Payment gateway integration — WC_Payment_Gateway class, process_payment()
- [ ] **WOO-04**: Shipping method development — WC_Shipping_Method class, calculate_shipping()
- [ ] **WOO-05**: WooCommerce hooks — woocommerce_before_cart, woocommerce_checkout_process, etc.
- [ ] **WOO-06**: Product data — custom fields via woocommerce_product_options_*, save hooks
- [ ] **WOO-07**: Order handling — WC_Order methods, status transitions, CRUD operations
- [ ] **WOO-08**: Cart operations — WC()->cart methods, cart item data, fees
- [ ] **WOO-09**: REST API extensions — WooCommerce REST API endpoints, custom endpoints
- [ ] **WOO-10**: Template overrides — woocommerce/ directory in themes, proper override patterns
- [ ] **WOO-11**: Shop page customization — archive-product.php, content-product.php patterns
- [ ] **WOO-12**: Cart/checkout theming — template parts, form field customization
- [ ] **WOO-13**: Product display patterns — single-product.php, gallery, variations
- [ ] **WOO-14**: WooCommerce blocks — product grid, cart block, checkout block integration
- [ ] **WOO-15**: Cart fragments performance — wc-cart-fragments.js, disable/optimize patterns
- [ ] **WOO-16**: High-order-volume patterns — HPOS (High-Performance Order Storage) compatibility
- [ ] **WOO-17**: WooCommerce query optimization — WC_Product_Query, wc_get_products() patterns
- [ ] **WOO-18**: Session handling — WC_Session_Handler, avoid custom sessions
- [ ] **WOO-19**: Checkout security — payment data handling, PCI considerations in custom code
- [ ] **WOO-20**: AJAX add-to-cart security — nonce verification, capability checks
- [ ] **WOO-21**: Coupon/discount validation — custom coupon types, validation hooks
- [ ] **WOO-22**: Search patterns for quick detection (grep commands)
- [ ] **WOO-23**: Code examples following WordPress PHP Coding Standards
- [ ] **WOO-24**: Severity levels and output format matching existing skill
- [ ] **WOO-25**: Common mistakes section (WooCommerce-specific false positives)
- [ ] **WOO-26**: Reference doc — WooCommerce extension development guide
- [ ] **WOO-27**: Reference doc — WooCommerce template and theming guide
- [ ] **WOO-28**: Reference doc — WooCommerce performance patterns
- [ ] **WOO-29**: Slash command /wp-woo-review (full review)
- [ ] **WOO-30**: Slash command /wp-woo (quick scan)

### Infrastructure Updates

- [ ] **INF-01**: Update README.md — all 5 new skills status ✅, trigger phrases, command docs
- [ ] **INF-02**: Update marketplace.json — register all new skills
- [ ] **INF-03**: Update plugin.json — version bump
- [ ] **INF-04**: Update CHANGELOG.md — document all new skills

## v2 Requirements

Deferred to future release. Tracked but not in current roadmap.

### Advanced Security

- **SEC-V2-01**: Magic method exploit detection (__toString, __destruct chains)
- **SEC-V2-02**: Security header generation (CSP, X-Frame-Options for plugin admin)

### Advanced Blocks

- **BLK-V2-01**: Block Slots API patterns (when standardized)
- **BLK-V2-02**: Block library performance profiling guidance

### Multisite

- **MS-01**: Multisite-specific patterns and network admin
- **MS-02**: Network-wide plugin activation patterns

## Out of Scope

| Feature | Reason |
|---------|--------|
| Server/infrastructure hardening | Claude reviews code, not server configs |
| Multisite skill | Niche use case, defer to v2 |
| Automated testing/CI | Plugin is documentation-only, no runtime |
| WordPress 5.x backward compat | Targeting WP 6.x+ modern APIs |
| CSS preprocessor patterns | Build tooling choice, not WP-specific |
| Page builder plugin patterns | Third-party tools, too many to cover |
| TypeScript block examples | Language choice, JS examples with TS note |

## Traceability

Which phases cover which requirements. Updated during roadmap creation.

| Requirement | Phase | Status |
|-------------|-------|--------|
| SEC-01 through SEC-29 | Phase 1 | Pending |
| PLG-01 through PLG-29 | Phase 2 | Pending |
| BLK-01 through BLK-30 | Phase 3 | Pending |
| THM-01 through THM-29 | Phase 4 | Pending |
| WOO-01 through WOO-30 | Phase 5 | Pending |
| INF-01 through INF-04 | Phase 6 | Pending |

**Coverage:**
- v1 requirements: 150 total
- Mapped to phases: 150
- Unmapped: 0 ✓

---
*Requirements defined: 2026-02-06*
*Last updated: 2026-02-06 after initial definition*
