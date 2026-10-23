# Campus-Desk-AI-Assistant
can help college students with notes, attendence and etc....

<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#4F46E5">
<title>Campus Desk | AI College Assistant & Academic Command Center</title>
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%234F46E5'><path d='M12 3L1 9l11 6 9-4.91V17h2V9L12 3zM5 13.18v4L12 21l7-3.82v-4L12 17l-7-3.82z'/></svg>">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400;1,600&family=Space+Grotesk:wght@500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ==========================================================================
   THEME TOKENS & DESIGN SYSTEM
   ========================================================================== */
:root {
  --font-sans: 'Plus Jakarta Sans', system-ui, -apple-system, sans-serif;
  --font-display: 'Space Grotesk', system-ui, -apple-system, sans-serif;
  --font-mono: 'JetBrains Mono', monospace;

  /* Light Theme */
  --bg: #F8FAFC;
  --bg-subtle: #F1F5F9;
  --surface: #FFFFFF;
  --surface-raised: #FFFFFF;
  --surface-hover: #F8FAFC;
  --ink: #0F172A;
  --ink-secondary: #475569;
  --ink-muted: #64748B;
  --ink-faint: #94A3B8;
  --line: #E2E8F0;
  --line-strong: #CBD5E1;

  /* Accent & Status */
  --brand: #4F46E5;
  --brand-hover: #4338CA;
  --brand-subtle: #EEF2FF;
  --brand-border: #C7D2FE;
  --brand-text: #3730A3;
  --on-brand: #FFFFFF;

  --ok: #059669;
  --ok-subtle: #ECFDF5;
  --ok-border: #A7F3D0;
  --warn: #D97706;
  --warn-subtle: #FFFBEB;
  --warn-border: #FDE68A;
  --bad: #E11D48;
  --bad-subtle: #FFF1F2;
  --bad-border: #FECDD3;
  --info: #0284C7;
  --info-subtle: #F0F9FF;
  --info-border: #BAE6FD;

  /* Elevation */
  --shadow-sm: 0 1px 2px 0 rgba(15, 23, 42, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(15, 23, 42, 0.07), 0 2px 4px -2px rgba(15, 23, 42, 0.05);
  --shadow-lg: 0 10px 15px -3px rgba(15, 23, 42, 0.08), 0 4px 6px -4px rgba(15, 23, 42, 0.04);
  --shadow-xl: 0 20px 25px -5px rgba(15, 23, 42, 0.09), 0 8px 10px -6px rgba(15, 23, 42, 0.04);
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 22px;
  --radius-full: 9999px;

  --header-h: 60px;
  --sidebar-w: 256px;
}

[data-theme="dark"] {
  --bg: #090D16;
  --bg-subtle: #0F1626;
  --surface: #131B2E;
  --surface-raised: #18223A;
  --surface-hover: #1E2945;
  --ink: #F8FAFC;
  --ink-secondary: #CBD5E1;
  --ink-muted: #94A3B8;
  --ink-faint: #64748B;
  --line: #1E293B;
  --line-strong: #334155;

  --brand: #6366F1;
  --brand-hover: #818CF8;
  --brand-subtle: rgba(99, 102, 241, 0.15);
  --brand-border: rgba(99, 102, 241, 0.3);
  --brand-text: #C7D2FE;
  --on-brand: #FFFFFF;

  --ok: #10B981;
  --ok-subtle: rgba(16, 185, 129, 0.15);
  --ok-border: rgba(16, 185, 129, 0.3);
  --warn: #F59E0B;
  --warn-subtle: rgba(245, 158, 11, 0.15);
  --warn-border: rgba(245, 158, 11, 0.3);
  --bad: #F43F5E;
  --bad-subtle: rgba(244, 63, 94, 0.15);
  --bad-border: rgba(244, 63, 94, 0.3);
  --info: #38BDF8;
  --info-subtle: rgba(56, 189, 248, 0.15);
  --info-border: rgba(56, 189, 248, 0.3);

  --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.4);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.5), 0 2px 4px -2px rgba(0, 0, 0, 0.4);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.6), 0 4px 6px -4px rgba(0, 0, 0, 0.5);
  --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.7), 0 8px 10px -6px rgba(0, 0, 0, 0.6);
}

@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]):not([data-theme="dark"]) {
    --bg: #090D16;
    --bg-subtle: #0F1626;
    --surface: #131B2E;
    --surface-raised: #18223A;
    --surface-hover: #1E2945;
    --ink: #F8FAFC;
    --ink-secondary: #CBD5E1;
    --ink-muted: #94A3B8;
    --ink-faint: #64748B;
    --line: #1E293B;
    --line-strong: #334155;

    --brand: #6366F1;
    --brand-hover: #818CF8;
    --brand-subtle: rgba(99, 102, 241, 0.15);
    --brand-border: rgba(99, 102, 241, 0.3);
    --brand-text: #C7D2FE;
    --on-brand: #FFFFFF;

    --ok: #10B981;
    --ok-subtle: rgba(16, 185, 129, 0.15);
    --ok-border: rgba(16, 185, 129, 0.3);
    --warn: #F59E0B;
    --warn-subtle: rgba(245, 158, 11, 0.15);
    --warn-border: rgba(245, 158, 11, 0.3);
    --bad: #F43F5E;
    --bad-subtle: rgba(244, 63, 94, 0.15);
    --bad-border: rgba(244, 63, 94, 0.3);
    --info: #38BDF8;
    --info-subtle: rgba(56, 189, 248, 0.15);
    --info-border: rgba(56, 189, 248, 0.3);

    --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.4);
    --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.5), 0 2px 4px -2px rgba(0, 0, 0, 0.4);
    --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.6), 0 4px 6px -4px rgba(0, 0, 0, 0.5);
    --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.7), 0 8px 10px -6px rgba(0, 0, 0, 0.6);
  }
}

/* Reduced Motion */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}

/* ==========================================================================
   RESET & BASE STYLES
   ========================================================================== */
*, *::before, *::after { box-sizing: border-box; }
html {
  font-family: var(--font-sans);
  background: var(--bg);
  color: var(--ink);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body {
  margin: 0;
  min-height: 100vh;
  min-height: 100dvh;
  display: flex;
  flex-direction: column;
}
h1, h2, h3, h4, h5 {
  font-family: var(--font-display);
  font-weight: 700;
  color: var(--ink);
  margin: 0;
  letter-spacing: -0.02em;
  line-height: 1.25;
}
p { margin: 0; }
a { color: var(--brand); text-decoration: none; }
a:hover { text-decoration: underline; }
button, input, select, textarea {
  font: inherit;
  color: inherit;
  outline: none;
}
button {
  cursor: pointer;
  background: none;
  border: none;
  padding: 0;
}
:focus-visible {
  outline: 2px solid var(--brand);
  outline-offset: 2px;
}

/* Form Controls */
input, select, textarea {
  width: 100%;
  padding: 10px 14px;
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius-md);
  font-size: 14px;
  color: var(--ink);
  transition: border-color 0.15s ease, box-shadow 0.15s ease;
}
input:focus, select:focus, textarea:focus {
  border-color: var(--brand);
  box-shadow: 0 0 0 3px var(--brand-subtle);
}
input::placeholder, textarea::placeholder {
  color: var(--ink-faint);
}

/* Utilities */
.mut { color: var(--ink-muted); }
.sm { font-size: 13px; }
.xs { font-size: 12px; }
.mono { font-family: var(--font-mono); }
.bold { font-weight: 600; }
.grow { flex: 1; min-width: 0; }
.truncate { white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }

/* System Warning Banner */
.sys-banner {
  background: var(--warn-subtle);
  border-bottom: 1px solid var(--warn-border);
  color: var(--warn);
  font-size: 12.5px;
  font-weight: 600;
  padding: 8px 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
}

/* ==========================================================================
   APP SHELL LAYOUT
   ========================================================================== */
.shell {
  display: grid;
  grid-template-columns: 1fr;
  min-height: 100vh;
  min-height: 100dvh;
}
@media (min-width: 960px) {
  .shell {
    grid-template-columns: var(--sidebar-w) 1fr;
  }
}

/* Sidebar */
.side {
  display: none;
}
@media (min-width: 960px) {
  .side {
    display: flex;
    flex-direction: column;
    height: 100vh;
    height: 100dvh;
    position: sticky;
    top: 0;
    background: var(--surface);
    border-right: 1px solid var(--line);
    padding: 20px 16px;
    gap: 16px;
    z-index: 20;
  }
}
.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 18px;
  color: var(--ink);
  padding: 2px 6px;
}
.brand-icon-box {
  width: 36px;
  height: 36px;
  border-radius: var(--radius-md);
  background: linear-gradient(135deg, var(--brand), #818CF8);
  color: #FFF;
  display: grid;
  place-items: center;
  flex-shrink: 0;
  box-shadow: 0 4px 10px rgba(79, 70, 229, 0.3);
}
.brand-icon-box svg { width: 20px; height: 20px; }
.brand-title {
  display: flex;
  flex-direction: column;
}
.brand-title span {
  font-size: 10.5px;
  font-family: var(--font-sans);
  color: var(--ink-muted);
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

/* Command Trigger in Sidebar */
.cmd-btn {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding: 9px 12px;
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  border-radius: var(--radius-md);
  color: var(--ink-muted);
  font-size: 13.5px;
  font-weight: 500;
  transition: all 0.15s ease;
}
.cmd-btn:hover {
  background: var(--surface-hover);
  border-color: var(--line-strong);
  color: var(--ink);
}
.kbd-pill {
  font-family: var(--font-mono);
  font-size: 11px;
  padding: 2px 6px;
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: 6px;
  color: var(--ink-muted);
  font-weight: 600;
}

/* Nav Menu */
.nav-group {
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.nav-item {
  display: flex;
  align-items: center;
  gap: 12px;
  width: 100%;
  padding: 10px 14px;
  border-radius: var(--radius-md);
  font-size: 14px;
  font-weight: 500;
  color: var(--ink-secondary);
  transition: background 0.15s ease, color 0.15s ease;
  text-align: left;
}
.nav-item svg { width: 19px; height: 19px; flex-shrink: 0; }
.nav-item:hover {
  background: var(--bg-subtle);
  color: var(--ink);
}
.nav-item.active {
  background: var(--brand-subtle);
  color: var(--brand);
  font-weight: 600;
}
.nav-badge {
  margin-left: auto;
  padding: 2px 7px;
  font-size: 11px;
  font-weight: 700;
  border-radius: var(--radius-full);
  background: var(--brand);
  color: #FFF;
}
.nav-badge.bad { background: var(--bad); }

/* Sidebar User Footer */
.side-footer {
  margin-top: auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding-top: 14px;
  border-top: 1px solid var(--line);
}
.user-card {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 8px 10px;
  border-radius: var(--radius-md);
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  text-align: left;
  transition: border-color 0.15s ease;
}
.user-card:hover {
  border-color: var(--brand-border);
}
.avatar {
  width: 34px;
  height: 34px;
  border-radius: var(--radius-full);
  background: linear-gradient(135deg, var(--brand), #4338CA);
  color: #FFF;
  font-weight: 700;
  font-size: 13.5px;
  display: grid;
  place-items: center;
  flex-shrink: 0;
}
.user-info { min-width: 0; }
.user-name { font-weight: 600; font-size: 13px; line-height: 1.2; }
.user-role { font-size: 11.5px; color: var(--ink-muted); }

/* Mobile Header */
.mobile-top {
  position: sticky;
  top: 0;
  z-index: 30;
  background: var(--surface);
  border-bottom: 1px solid var(--line);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 8px 16px;
  height: var(--header-h);
}
@media (min-width: 960px) {
  .mobile-top { display: none; }
}

/* Mobile Bottom Navigation (Strict 5 items) */
.mobile-tabs {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 30;
  background: var(--surface);
  border-top: 1px solid var(--line);
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  padding: 6px 4px calc(6px + env(safe-area-inset-bottom, 0px));
}
@media (min-width: 960px) {
  .mobile-tabs { display: none; }
}
.tab-btn {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 3px;
  font-size: 11px;
  font-weight: 500;
  color: var(--ink-muted);
  padding: 6px 0;
  border-radius: var(--radius-sm);
  transition: color 0.15s ease;
  min-width: 0;
}
.tab-btn span {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  max-width: 100%;
}
.tab-btn.active {
  color: var(--brand);
  font-weight: 600;
}
.tab-btn svg { width: 19px; height: 19px; flex-shrink: 0; }

/* Mobile More Drawer Sheet */
.more-sheet {
  position: fixed;
  inset: 0;
  z-index: 45;
  background: rgba(15, 23, 42, 0.5);
  backdrop-filter: blur(4px);
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.2s ease;
}
.more-sheet.open {
  opacity: 1;
  pointer-events: auto;
}
.more-sheet-content {
  background: var(--surface);
  border-top-left-radius: var(--radius-xl);
  border-top-right-radius: var(--radius-xl);
  padding: 24px 20px calc(24px + env(safe-area-inset-bottom, 0px));
  display: flex;
  flex-direction: column;
  gap: 12px;
  transform: translateY(100%);
  transition: transform 0.25s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: var(--shadow-xl);
}
.more-sheet.open .more-sheet-content {
  transform: translateY(0);
}
.more-sheet-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
.more-menu-btn {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 12px 14px;
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  border-radius: var(--radius-md);
  font-size: 13.5px;
  font-weight: 600;
  color: var(--ink);
  text-align: left;
}
.more-menu-btn svg { width: 18px; height: 18px; color: var(--brand); }

/* Main Wrapper */
.main-wrapper {
  min-width: 0;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  min-height: 100dvh;
}
.content-container {
  padding: 20px 16px 110px;
  max-width: 1240px;
  width: 100%;
  margin: 0 auto;
}
@media (min-width: 960px) {
  .content-container {
    padding: 34px 44px 60px;
  }
}

/* Page Header */
.page-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 24px;
  flex-wrap: wrap;
}
.page-title {
  font-size: clamp(23px, 3.2vw, 30px);
  font-weight: 800;
  color: var(--ink);
  letter-spacing: -0.025em;
}
.page-sub {
  color: var(--ink-muted);
  font-size: 14px;
  margin-top: 4px;
}
.actions-row {
  display: flex;
  align-items: center;
  gap: 10px;
  flex-wrap: wrap;
}

/* ==========================================================================
   BUTTONS & CONTROLS
   ========================================================================== */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  padding: 9px 16px;
  border-radius: var(--radius-md);
  font-size: 13.5px;
  font-weight: 600;
  border: 1px solid var(--line);
  background: var(--surface);
  color: var(--ink);
  transition: all 0.15s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: var(--shadow-sm);
  white-space: nowrap;
}
.btn svg { width: 17px; height: 17px; flex-shrink: 0; }
.btn:hover {
  background: var(--bg-subtle);
  border-color: var(--line-strong);
  transform: translateY(-1px);
}
.btn:active {
  transform: translateY(0);
}
.btn:disabled {
  opacity: 0.55;
  cursor: not-allowed;
  transform: none;
}
.btn.primary {
  background: var(--brand);
  border-color: var(--brand);
  color: #FFF;
  box-shadow: 0 4px 12px rgba(79, 70, 229, 0.25);
}
.btn.primary:hover {
  background: var(--brand-hover);
  border-color: var(--brand-hover);
}
.btn.danger {
  background: var(--bad-subtle);
  border-color: var(--bad-border);
  color: var(--bad);
}
.btn.danger:hover {
  background: var(--bad);
  color: #FFF;
}
.btn.ghost {
  background: transparent;
  border-color: transparent;
  box-shadow: none;
  color: var(--ink-secondary);
}
.btn.ghost:hover {
  background: var(--bg-subtle);
  color: var(--ink);
}
.btn.sm {
  padding: 6px 12px;
  font-size: 12.5px;
  border-radius: var(--radius-sm);
}

.icon-btn {
  width: 36px;
  height: 36px;
  display: grid;
  place-items: center;
  border-radius: var(--radius-md);
  border: 1px solid var(--line);
  background: var(--surface);
  color: var(--ink-secondary);
  transition: all 0.15s ease;
  flex-shrink: 0;
}
.icon-btn:hover {
  background: var(--bg-subtle);
  color: var(--ink);
  border-color: var(--line-strong);
}
.icon-btn svg { width: 18px; height: 18px; }
.icon-btn.active {
  background: var(--brand-subtle);
  color: var(--brand);
  border-color: var(--brand-border);
}
.icon-btn.listening {
  background: var(--bad-subtle);
  color: var(--bad);
  border-color: var(--bad-border);
  animation: pulseMic 1.5s infinite;
}
@keyframes pulseMic {
  0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(225, 29, 72, 0.4); }
  70% { transform: scale(1.06); box-shadow: 0 0 0 8px rgba(225, 29, 72, 0); }
  100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(225, 29, 72, 0); }
}

/* Segmented Control / Filter Bars */
.segmented {
  display: inline-flex;
  padding: 4px;
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  border-radius: var(--radius-md);
  gap: 3px;
  overflow-x: auto;
  max-width: 100%;
}
.seg-btn {
  padding: 6px 13px;
  font-size: 13px;
  font-weight: 500;
  color: var(--ink-muted);
  border-radius: 7px;
  transition: all 0.15s ease;
  white-space: nowrap;
}
.seg-btn:hover { color: var(--ink); }
.seg-btn.active {
  background: var(--surface);
  color: var(--ink);
  font-weight: 600;
  box-shadow: var(--shadow-sm);
}
.seg-btn.active.ok {
  background: var(--ok-subtle);
  color: var(--ok);
}
.seg-btn.active.bad {
  background: var(--bad-subtle);
  color: var(--bad);
}

/* Badges & Chips */
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 3px 10px;
  border-radius: var(--radius-full);
  font-size: 12px;
  font-weight: 600;
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  color: var(--ink-secondary);
}
.badge.primary { background: var(--brand-subtle); border-color: var(--brand-border); color: var(--brand); }
.badge.ok { background: var(--ok-subtle); border-color: var(--ok-border); color: var(--ok); }
.badge.warn { background: var(--warn-subtle); border-color: var(--warn-border); color: var(--warn); }
.badge.bad { background: var(--bad-subtle); border-color: var(--bad-border); color: var(--bad); }
.badge.neutral { background: var(--bg-subtle); border-color: var(--line); color: var(--ink-muted); }
.badge-dot {
  width: 7px;
  height: 7px;
  border-radius: var(--radius-full);
  background: currentColor;
  flex-shrink: 0;
}

/* ==========================================================================
   CARDS & GRIDS
   ========================================================================== */
.card {
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius-lg);
  padding: 22px;
  box-shadow: var(--shadow-sm);
  position: relative;
  transition: border-color 0.15s ease;
}
.card:hover {
  border-color: var(--line-strong);
}
.card-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  margin-bottom: 16px;
}
.card-head h2, .card-head h3 {
  font-size: 17px;
  font-weight: 700;
}
.grid { display: grid; gap: 18px; }
.g2 { grid-template-columns: 1fr; }
@media (min-width: 860px) {
  .g2 { grid-template-columns: 1fr 1fr; }
}

/* ==========================================================================
   HOMEPAGE WIDGETS
   ========================================================================== */
.hero-card {
  background: linear-gradient(135deg, #1E1B4B 0%, #312E81 50%, #4338CA 100%);
  color: #FFF;
  border-radius: var(--radius-lg);
  padding: 24px;
  position: relative;
  overflow: hidden;
  box-shadow: 0 10px 25px -5px rgba(49, 46, 129, 0.4);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 200px;
}
.hero-tag {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 4px 11px;
  background: rgba(255,255,255,0.16);
  backdrop-filter: blur(8px);
  border-radius: var(--radius-full);
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.03em;
  text-transform: uppercase;
  margin-bottom: 12px;
  width: fit-content;
}
.hero-subject {
  font-size: clamp(21px, 3vw, 27px);
  font-weight: 800;
  letter-spacing: -0.02em;
  line-height: 1.25;
}
.hero-meta {
  display: flex;
  align-items: center;
  gap: 14px;
  margin-top: 10px;
  font-size: 13.5px;
  color: rgba(255,255,255,0.88);
  flex-wrap: wrap;
}
.hero-meta-item {
  display: inline-flex;
  align-items: center;
  gap: 5px;
}
.hero-meta-item svg { width: 16px; height: 16px; opacity: 0.9; }

/* Hero Present Mark Button */
.hero-mark-btn {
  background: #FFFFFF;
  color: #1E1B4B;
  border-color: #FFFFFF;
  font-weight: 700;
}
.hero-mark-btn.marked {
  background: #10B981;
  color: #FFFFFF;
  border-color: #10B981;
}

/* Campus Status Ticker */
.campus-ticker {
  display: flex;
  align-items: center;
  gap: 10px;
  overflow-x: auto;
  padding-bottom: 4px;
  margin-bottom: 18px;
  scrollbar-width: none;
}
.campus-ticker::-webkit-scrollbar { display: none; }
.ticker-pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 14px;
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius-full);
  font-size: 12.5px;
  font-weight: 500;
  color: var(--ink-secondary);
  white-space: nowrap;
  box-shadow: var(--shadow-sm);
}
.ticker-pill svg { width: 15px; height: 15px; color: var(--brand); flex-shrink: 0; }
.ticker-pill b { color: var(--ink); font-weight: 600; }
.live-dot {
  width: 8px;
  height: 8px;
  border-radius: var(--radius-full);
  background: var(--ok);
  box-shadow: 0 0 0 2px var(--ok-subtle);
  animation: pulseLive 2s infinite;
}
@keyframes pulseLive {
  0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.5); }
  70% { transform: scale(1); box-shadow: 0 0 0 6px rgba(16, 185, 129, 0); }
  100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(16, 185, 129, 0); }
}

/* Attendance Ring */
.att-snap-grid {
  display: flex;
  align-items: center;
  gap: 20px;
}
.ring-wrap {
  position: relative;
  flex-shrink: 0;
}
.ring-svg {
  transform: rotate(-90deg);
}
.ring-bg { stroke: var(--line); }
.ring-fg {
  stroke-linecap: round;
  transition: stroke-dasharray 0.5s ease;
}
.ring-center {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.ring-pct {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 25px;
  color: var(--ink);
  line-height: 1;
}
.ring-lbl {
  font-size: 11px;
  font-weight: 600;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin-top: 2px;
}

/* Rows */
.class-row {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 13px 0;
  border-top: 1px solid var(--line);
}
.class-row:first-child { border-top: 0; padding-top: 0; }
.class-color-bar {
  width: 4px;
  height: 38px;
  border-radius: var(--radius-full);
  background: var(--c);
  flex-shrink: 0;
}
.class-title {
  font-weight: 600;
  font-size: 14.5px;
  color: var(--ink);
}
.class-sub {
  font-size: 12.5px;
  color: var(--ink-muted);
  margin-top: 2px;
}

.task-row {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  padding: 13px 0;
  border-top: 1px solid var(--line);
  transition: opacity 0.2s ease;
}
.task-row:first-child { border-top: 0; padding-top: 0; }
.task-row.done { opacity: 0.55; }
.task-check {
  width: 22px;
  height: 22px;
  border-radius: 6px;
  border: 2px solid var(--line-strong);
  display: grid;
  place-items: center;
  color: transparent;
  flex-shrink: 0;
  margin-top: 2px;
  transition: all 0.15s ease;
}
.task-check:hover {
  border-color: var(--brand);
}
.task-check.checked {
  background: var(--ok);
  border-color: var(--ok);
  color: #FFF;
}
.task-title {
  font-weight: 600;
  font-size: 14px;
  color: var(--ink);
}
.task-row.done .task-title {
  text-decoration: line-through;
}
.task-meta {
  display: flex;
  align-items: center;
  gap: 7px;
  flex-wrap: wrap;
  margin-top: 4px;
  font-size: 12px;
}

/* ==========================================================================
   TIMETABLE VIEW
   ========================================================================== */
.week-grid {
  display: grid;
  gap: 14px;
  grid-template-columns: 1fr;
}
@media (min-width: 680px) and (max-width: 1099px) {
  .week-grid { grid-template-columns: repeat(2, 1fr); }
}
@media (min-width: 1100px) {
  .week-grid { grid-template-columns: repeat(6, 1fr); }
}
.day-column {
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  border-radius: var(--radius-md);
  padding: 14px 12px;
  min-height: 180px;
  display: flex;
  flex-direction: column;
  gap: 9px;
}
.day-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-bottom: 8px;
  border-bottom: 1px solid var(--line);
  margin-bottom: 2px;
}
.day-title {
  font-weight: 700;
  font-size: 13.5px;
  color: var(--ink);
}
.class-card-tt {
  background: var(--surface);
  border: 1px solid var(--line);
  border-left: 4px solid var(--c);
  border-radius: var(--radius-md);
  padding: 11px;
  text-align: left;
  transition: all 0.15s ease;
  box-shadow: var(--shadow-sm);
}
.class-card-tt:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
  border-color: var(--line-strong);
}
.tt-subj { font-weight: 700; font-size: 13px; color: var(--ink); }
.tt-time { font-size: 11.5px; color: var(--ink-muted); margin-top: 3px; }
.tt-room { font-size: 11.5px; font-weight: 600; color: var(--brand); margin-top: 3px; }

/* ==========================================================================
   ATTENDANCE VIEW
   ========================================================================== */
.att-card {
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius-lg);
  padding: 18px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 13px;
  box-shadow: var(--shadow-sm);
  transition: border-color 0.15s ease;
}
.att-card:hover {
  border-color: var(--line-strong);
}
.att-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 12px;
}
.att-subj-wrap {
  display: flex;
  align-items: center;
  gap: 10px;
}
.att-dot {
  width: 12px;
  height: 12px;
  border-radius: var(--radius-full);
  background: var(--c);
  flex-shrink: 0;
}
.att-big-pct {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 28px;
  line-height: 1;
}
.att-big-pct.ok { color: var(--ok); }
.att-big-pct.warn { color: var(--warn); }
.att-big-pct.bad { color: var(--bad); }

.bar-track {
  height: 9px;
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  border-radius: var(--radius-full);
  overflow: hidden;
  position: relative;
}
.bar-fill {
  height: 100%;
  border-radius: var(--radius-full);
  transition: width 0.3s ease;
}
.bar-target-tick {
  position: absolute;
  top: 0;
  bottom: 0;
  width: 2px;
  background: var(--ink);
  opacity: 0.6;
  z-index: 2;
}
.bunk-verdict {
  padding: 9px 12px;
  border-radius: var(--radius-md);
  font-size: 13px;
  font-weight: 500;
  line-height: 1.4;
}
.bunk-verdict.ok { background: var(--ok-subtle); color: var(--ok); }
.bunk-verdict.warn { background: var(--warn-subtle); color: var(--warn); }
.bunk-verdict.bad { background: var(--bad-subtle); color: var(--bad); }

/* ==========================================================================
   NOTES & EDITOR VIEW
   ========================================================================== */
.notes-layout {
  display: grid;
  gap: 18px;
  grid-template-columns: 1fr;
}
@media (min-width: 900px) {
  .notes-layout {
    grid-template-columns: 320px 1fr;
    align-items: start;
  }
}
.notes-sidebar {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.note-list-card {
  padding: 12px;
  max-height: calc(100vh - 230px);
  max-height: calc(100dvh - 230px);
  overflow-y: auto;
}
.note-item {
  width: 100%;
  text-align: left;
  padding: 11px 12px;
  border-radius: var(--radius-md);
  background: transparent;
  border: 1px solid transparent;
  transition: background 0.15s ease;
  margin-bottom: 5px;
}
.note-item:hover {
  background: var(--bg-subtle);
}
.note-item.active {
  background: var(--brand-subtle);
  border-color: var(--brand-border);
}
.note-item-title {
  font-weight: 600;
  font-size: 13.5px;
  color: var(--ink);
  display: flex;
  align-items: center;
  gap: 6px;
}
.note-item-preview {
  font-size: 12px;
  color: var(--ink-muted);
  margin-top: 3px;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.note-editor-card {
  padding: 22px;
  min-height: 500px;
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.note-title-input {
  font-family: var(--font-display);
  font-size: 24px;
  font-weight: 700;
  border: none;
  background: transparent;
  padding: 0;
  color: var(--ink);
}
.note-title-input:focus {
  box-shadow: none;
  border-bottom: 2px solid var(--brand);
  border-radius: 0;
}
.note-body-textarea {
  flex: 1;
  min-height: 320px;
  border: 1px solid var(--line);
  background: var(--bg-subtle);
  border-radius: var(--radius-md);
  padding: 14px;
  font-size: 14.5px;
  line-height: 1.6;
  color: var(--ink);
  resize: vertical;
}

/* ==========================================================================
   CHAT / ASK AI VIEW
   ========================================================================== */
.chat-window {
  display: flex;
  flex-direction: column;
  height: calc(100vh - 220px);
  height: calc(100dvh - 220px);
  min-height: 500px;
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
}
.chat-messages {
  flex: 1;
  overflow-y: auto;
  padding: 20px 18px;
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.msg-row {
  display: flex;
  gap: 10px;
  max-width: 820px;
}
.msg-row.user {
  margin-left: auto;
  flex-direction: row-reverse;
}
.msg-avatar {
  width: 32px;
  height: 32px;
  border-radius: var(--radius-full);
  display: grid;
  place-items: center;
  font-size: 13px;
  font-weight: 700;
  flex-shrink: 0;
}
.msg-row.assistant .msg-avatar {
  background: var(--brand-subtle);
  color: var(--brand);
}
.msg-row.user .msg-avatar {
  background: var(--brand);
  color: #FFF;
}
.msg-bubble {
  padding: 12px 16px;
  border-radius: var(--radius-lg);
  font-size: 14px;
  line-height: 1.55;
}
.msg-row.assistant .msg-bubble {
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  color: var(--ink);
  border-top-left-radius: 4px;
}
.msg-row.user .msg-bubble {
  background: var(--brand);
  color: #FFF;
  border-top-right-radius: 4px;
}
.msg-bubble p { margin-bottom: 6px; }
.msg-bubble p:last-child { margin-bottom: 0; }
.msg-bubble ul, .msg-bubble ol { margin: 6px 0; padding-left: 20px; }
.msg-bubble li { margin-bottom: 3px; }
.msg-bubble code {
  font-family: var(--font-mono);
  font-size: 12px;
  padding: 2px 5px;
  border-radius: 4px;
  background: rgba(0,0,0,0.06);
}
[data-theme="dark"] .msg-bubble code {
  background: rgba(255,255,255,0.1);
}
.code-block {
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius-md);
  padding: 12px;
  font-family: var(--font-mono);
  font-size: 12.5px;
  overflow-x: auto;
  margin: 8px 0;
}
.chat-prompts-bar {
  display: flex;
  gap: 8px;
  padding: 10px 18px;
  overflow-x: auto;
  background: var(--surface);
  border-top: 1px solid var(--line);
  scrollbar-width: none;
}
.prompt-chip {
  padding: 6px 13px;
  border-radius: var(--radius-full);
  background: var(--bg-subtle);
  border: 1px solid var(--line);
  font-size: 12.5px;
  font-weight: 500;
  color: var(--ink-secondary);
  white-space: nowrap;
  transition: all 0.15s ease;
}
.prompt-chip:hover {
  background: var(--brand-subtle);
  color: var(--brand);
  border-color: var(--brand-border);
}
.chat-input-bar {
  padding: 14px 18px;
  background: var(--surface);
  border-top: 1px solid var(--line);
  display: flex;
  gap: 10px;
  align-items: flex-end;
}
.chat-textarea {
  min-height: 42px;
  max-height: 140px;
  resize: none;
  padding: 10px 12px;
  line-height: 1.4;
}

/* ==========================================================================
   TOOLS (POMODORO, FLASHCARDS, GPA, LOOKUP)
   ========================================================================== */
.pomo-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 36px 20px;
  text-align: center;
}
.pomo-time-display {
  font-family: var(--font-display);
  font-size: clamp(60px, 9vw, 84px);
  font-weight: 800;
  letter-spacing: -0.04em;
  color: var(--ink);
  line-height: 1;
  margin: 14px 0;
}

/* 3D Flashcard Flip */
.flashcard-stage {
  perspective: 1000px;
  min-height: 250px;
  cursor: pointer;
  user-select: none;
}
.flashcard-inner {
  min-height: 250px;
  position: relative;
  border-radius: var(--radius-lg);
  border: 1px solid var(--line);
  background: var(--surface);
  transform-style: preserve-3d;
  transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: var(--shadow-md);
}
.flashcard-stage.flipped .flashcard-inner {
  transform: rotateY(180deg);
}
.flashcard-face {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 32px 24px;
  text-align: center;
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
  border-radius: var(--radius-lg);
}
.flashcard-back {
  transform: rotateY(180deg);
  background: var(--brand-subtle);
  border: 1px solid var(--brand-border);
}

/* GPA Grid Responsive */
.gpa-grid-row {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr auto;
  gap: 10px;
  align-items: center;
  padding: 8px 0;
  border-top: 1px solid var(--line);
}
@media (max-width: 540px) {
  .gpa-grid-row {
    grid-template-columns: 1fr 1fr;
    gap: 8px;
    padding: 12px 0;
  }
}

/* ==========================================================================
   MODALS & SEARCH PALETTE
   ========================================================================== */
dialog {
  border: none;
  padding: 0;
  border-radius: var(--radius-xl);
  background: var(--surface);
  color: var(--ink);
  width: min(520px, calc(100vw - 32px));
  max-height: calc(100vh - 48px);
  max-height: calc(100dvh - 48px);
  box-shadow: var(--shadow-xl);
  margin: auto;
}
dialog::backdrop {
  background: rgba(15, 23, 42, 0.6);
  backdrop-filter: blur(4px);
}
.modal-form {
  padding: 24px 26px;
  display: flex;
  flex-direction: column;
  gap: 15px;
}
.modal-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.modal-header h2 { font-size: 19px; font-weight: 700; }
.form-field {
  display: flex;
  flex-direction: column;
  gap: 5px;
}
.form-field label, .form-field .field-lbl {
  font-size: 13px;
  font-weight: 600;
  color: var(--ink-secondary);
}
.form-row2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}
@media (max-width: 480px) {
  .form-row2 { grid-template-columns: 1fr; }
}
.color-picker-row {
  display: flex;
  gap: 9px;
  flex-wrap: wrap;
}
.color-swatch-label {
  position: relative;
  cursor: pointer;
}
.color-swatch-label input {
  position: absolute;
  opacity: 0;
  pointer-events: none;
}
.color-circle {
  width: 30px;
  height: 30px;
  border-radius: var(--radius-full);
  background: var(--c);
  display: block;
  transition: transform 0.15s ease;
}
.color-swatch-label input:checked + .color-circle {
  outline: 3px solid var(--ink);
  outline-offset: 3px;
  transform: scale(1.1);
}

/* Command Palette */
.cmd-modal {
  width: min(580px, calc(100vw - 32px));
  border-radius: var(--radius-lg);
  overflow: hidden;
}
.cmd-input-wrap {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 15px 18px;
  border-bottom: 1px solid var(--line);
}
.cmd-input-wrap svg { width: 19px; height: 19px; color: var(--ink-muted); flex-shrink: 0; }
.cmd-input {
  border: none;
  background: transparent;
  font-size: 15px;
  padding: 0;
}
.cmd-input:focus { box-shadow: none; }
.cmd-results {
  max-height: 340px;
  overflow-y: auto;
  padding: 8px;
}
.cmd-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding: 9px 12px;
  border-radius: var(--radius-md);
  font-size: 13.5px;
  font-weight: 500;
  color: var(--ink);
  transition: all 0.1s ease;
  text-align: left;
}
.cmd-item.selected, .cmd-item:hover {
  background: var(--brand-subtle);
  color: var(--brand);
}

/* Toast */
#toast {
  position: fixed;
  bottom: calc(84px + env(safe-area-inset-bottom, 0px));
  left: 50%;
  transform: translateX(-50%) translateY(20px);
  background: var(--ink);
  color: var(--bg);
  padding: 11px 20px;
  border-radius: var(--radius-full);
  font-size: 13.5px;
  font-weight: 600;
  box-shadow: var(--shadow-lg);
  z-index: 100;
  opacity: 0;
  pointer-events: none;
  transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
}
#toast.show {
  opacity: 1;
  transform: translateX(-50%) translateY(0);
}
@media (min-width: 960px) {
  #toast { bottom: 28px; }
}

/* Confetti */
.confetti-box {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 99;
  overflow: hidden;
}
.confetti-piece {
  position: absolute;
  top: -10px;
  width: 9px;
  height: 13px;
  border-radius: 2px;
  animation: confettiFall 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
}
@keyframes confettiFall {
  to { transform: translateY(115vh) rotate(540deg); opacity: 0; }
}
</style>
</head>
<body>

<div id="storage-alert" class="sys-banner" style="display:none">
  <span>⚠️ Local storage is restricted in this private browsing session. Data will not persist after reload.</span>
  <button class="btn sm ghost" onclick="this.parentElement.style.display='none'">Dismiss</button>
</div>

<div id="app"></div>

<!-- Mobile More Navigation Drawer -->
<div id="more-sheet" class="more-sheet" role="dialog" aria-label="More navigation options">
  <div class="more-sheet-content">
    <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:6px">
      <h3 style="font-size:16px">Campus Desk Modules</h3>
      <button class="icon-btn" data-act="more-close" aria-label="Close menu"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 18L18 6M6 6l12 12"/></svg></button>
    </div>
    <div class="more-sheet-grid">
      <button class="more-menu-btn" data-act="nav" data-v="notes"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"/></svg> Lecture Notes</button>
      <button class="more-menu-btn" data-act="nav" data-v="chat"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z"/></svg> Ask AI Copilot</button>
      <button class="more-menu-btn" data-act="nav" data-v="tools"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"/></svg> Study Tools</button>
      <button class="more-menu-btn" data-act="nav" data-v="alerts"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"/></svg> Alerts</button>
      <button class="more-menu-btn" data-act="profile"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z M15 12a3 3 0 11-6 0 3 3 0 016 0z"/></svg> Settings</button>
      <button class="more-menu-btn" data-act="theme-toggle"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"/></svg> Theme Toggle</button>
    </div>
  </div>
</div>

<dialog id="modal"></dialog>
<dialog id="cmd" class="cmd-modal" aria-label="Command search"></dialog>
<div id="toast" role="status" aria-live="polite"></div>
<div id="confetti" class="confetti-box" hidden></div>

<script>
(() => {
'use strict';
/* Campus Desk v2.2 – fixes: safer md(), notif cache, Gemini key clear, focus restore, keyboard shortcuts, save feedback */

/* ==========================================================================
   SAFE STORAGE & ESCAPING UTILITIES
   ========================================================================== */
const $ = (s, r = document) => r.querySelector(s);
const $$ = (s, r = document) => Array.from(r.querySelectorAll(s));
const esc = s => String(s ?? '').replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
const pad = n => String(n).padStart(2, '0');
const uid = () => Math.random().toString(36).slice(2, 9) + Date.now().toString(36).slice(-3);

/** Resize / compress an image File to a reasonable dataURL for localStorage */
function fileToCompressedDataUrl(file, maxSide = 1280, quality = 0.72) {
  return new Promise((resolve, reject) => {
    if (!file || !file.type.startsWith('image/')) {
      reject(new Error('Not an image'));
      return;
    }
    const reader = new FileReader();
    reader.onerror = () => reject(new Error('Failed to read file'));
    reader.onload = () => {
      const img = new Image();
      img.onerror = () => reject(new Error('Invalid image'));
      img.onload = () => {
        let w = img.width, h = img.height;
        if (w > maxSide || h > maxSide) {
          if (w > h) { h = Math.round(h * maxSide / w); w = maxSide; }
          else { w = Math.round(w * maxSide / h); h = maxSide; }
        }
        const canvas = document.createElement('canvas');
        canvas.width = w;
        canvas.height = h;
        const ctx = canvas.getContext('2d');
        ctx.drawImage(img, 0, 0, w, h);
        // Prefer JPEG for photos; keep PNG for screenshots with transparency if small
        const mime = (file.type === 'image/png' && file.size < 400000) ? 'image/png' : 'image/jpeg';
        resolve(canvas.toDataURL(mime, quality));
      };
      img.src = reader.result;
    };
    reader.readAsDataURL(file);
  });
}
const plural = (n, a, b) => n === 1 ? a : b;

const isMac = typeof navigator !== 'undefined' && /Mac|iPhone|iPad|iPod/.test(navigator.platform || navigator.userAgent);
const cmdKeyText = isMac ? '⌘K' : 'Ctrl K';

let storageAvailable = true;
try {
  localStorage.setItem('__cd_test', '1');
  localStorage.removeItem('__cd_test');
} catch (e) {
  storageAvailable = false;
  setTimeout(() => {
    const el = $('#storage-alert');
    if (el) el.style.display = 'flex';
  }, 100);
}

const mem = {};
const store = {
  get(k, d) {
    if (storageAvailable) {
      try {
        const v = localStorage.getItem(k);
        if (v != null) return JSON.parse(v);
      } catch (e) {}
    }
    return (k in mem) ? mem[k] : d;
  },
  set(k, v) {
    mem[k] = v;
    if (storageAvailable) {
      try { localStorage.setItem(k, JSON.stringify(v)); } catch (e) {}
    }
  }
};

const DAYS = ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'];
const FULLDAYS = ['Monday','Tuesday','Wednesday','Thursday','Friday','Saturday','Sunday'];
const dow = d => (d.getDay() + 6) % 7; // 0=Mon ... 6=Sun
const iso = d => `${d.getFullYear()}-${pad(d.getMonth()+1)}-${pad(d.getDate())}`;

const toMin = t => {
  if (!t || typeof t !== 'string') return 0;
  const [h, m] = t.split(':').map(Number);
  return (h || 0) * 60 + (m || 0);
};

const fmtT = t => {
  if (!t) return '';
  let [h, m] = t.split(':').map(Number);
  const ap = h >= 12 ? 'PM' : 'AM';
  h = h % 12 || 12;
  return `${h}:${pad(m)} ${ap}`;
};

const byStart = (a, b) => toMin(a.start) - toMin(b.start);
const dur = m => m < 60 ? `${m}m` : `${Math.floor(m/60)}h${m % 60 ? ' ' + (m % 60) + 'm' : ''}`;

const fmtDue = s => {
  if (!s) return 'No due date';
  const d = new Date(s);
  if (isNaN(d)) return 'Invalid date';
  return d.toLocaleString(undefined, { weekday:'short', month:'short', day:'numeric', hour:'numeric', minute:'2-digit' });
};

function rel(ms) {
  const m = Math.round(ms / 60000), a = Math.abs(m);
  let s;
  if (a < 60) s = `${a} min`;
  else if (a < 2880) s = `${Math.round(a / 60)} hr`;
  else s = `${Math.round(a / 1440)} days`;
  return m >= 0 ? `in ${s}` : `${s} ago`;
}

const COLORS = ['#4F46E5','#059669','#D97706','#DC2626','#7C3AED','#0284C7','#DB2777','#16A34A'];
const GRADE_PT = { 'O':10,'A+':9,'A':8,'B+':7,'B':6,'C':5,'P':4,'F':0 };

/* ==========================================================================
   ICONS SYSTEM
   ========================================================================== */
const ICON = {
  home: 'M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6',
  calendar: 'M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z',
  check: 'M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z',
  tasks: 'M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-6 9l2 2 4-4',
  notes: 'M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10',
  chat: 'M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z',
  spark: 'M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z',
  bell: 'M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9',
  plus: 'M12 4v16m8-8H4',
  search: 'M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z',
  settings: 'M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z M15 12a3 3 0 11-6 0 3 3 0 016 0z',
  sun: 'M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z',
  cloud: 'M3 15a4 4 0 004 4h11a3 3 0 001.32-5.69A5 5 0 0016 7a5 5 0 00-4.9 4.02A4.002 4.002 0 003 15z',
  rain: 'M16 13v6m-4-6v6m-4-6v6M3 13a4 4 0 014-4h1a5 5 0 019.9 1A3 3 0 0119 13',
  snow: 'M8 15h.01M12 15h.01M16 15h.01M10 18h.01M14 18h.01M3 13a4 4 0 014-4h1a5 5 0 019.9 1A3 3 0 0119 13',
  thunder: 'M13 10V3L4 14h7v7l9-11h-7z',
  send: 'M12 19l9 2-9-18-9 18 9-2zm0 0v-8',
  mic: 'M19 11a7 7 0 01-7 7m0 0a7 7 0 01-7-7m7 7v4m0 0H8m4 0h4m-4-8a3 3 0 01-3-3V5a3 3 0 116 0v6a3 3 0 01-3 3z',
  pin: 'M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z',
  trash: 'M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16',
  edit: 'M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z',
  clock: 'M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z',
  tick: 'M5 13l4 4L19 7',
  x: 'M6 18L18 6M6 6l12 12',
  more: 'M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z'
};
const icon = (n, w = 18) => `<svg width="${w}" height="${w}" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="${ICON[n] || ICON.home}"/></svg>`;

/* ==========================================================================
   DEFAULT STATE & MODEL DEFAULTS
   ========================================================================== */
const defaultSettings = () => ({
  target: 75,
  dueHours: 48,
  city: 'Pune',
  geminiKey: '',
  theme: 'system',
  notify: false,
  focusMin: 25,
  breakMin: 5
});

const emptyData = () => ({
  subjects: [],
  timetable: [],
  assignments: [],
  notes: [],
  marks: {},
  grades: [],
  dismissed: [],
  settings: defaultSettings()
});

const S = {
  user: null,
  data: null,
  view: 'home',
  ttDay: (() => { const d = dow(new Date()); return d > 5 ? 0 : d; })(),
  ttFilter: 'all', // 'all' or day index 0..6
  asFilter: 'pending',
  noteId: null,
  noteQ: '',
  chat: [],
  busy: false,
  noteAI: {},
  authTab: 'in',
  reset: null,
  toolsTab: 'study',
  weather: null,
  quote: null,
  holidays: [],
  apiOk: {},
  lookupQ: '',
  lookup: null,
  wiki: null,
  lookupBusy: false,
  pomo: { run: false, mode: 'focus', left: 25 * 60, targetEndTime: null, done: 0, customFocus: 25, customBreak: 5 },
  cards: [],
  cardI: 0,
  rec: null,
  cmdI: 0
};

const getUsers = () => store.get('cd:users', []);
const save = () => { 
  if (S.user) store.set('cd:data:' + S.user.id, S.data); 
  _notifCache = null; // invalidate notification cache
};
let saveDebounceTimer = null;
const saveSoon = () => { clearTimeout(saveDebounceTimer); saveDebounceTimer = setTimeout(save, 300); };

const loadData = id => {
  const d = store.get('cd:data:' + id, null) || {};
  const base = emptyData();
  const merged = Object.assign(base, d);
  merged.settings = Object.assign(defaultSettings(), d.settings || {});
  if (!Array.isArray(merged.dismissed)) merged.dismissed = [];
  if (!Array.isArray(merged.grades)) merged.grades = [];
  if (!Array.isArray(merged.subjects)) merged.subjects = [];
  if (!Array.isArray(merged.timetable)) merged.timetable = [];
  if (!Array.isArray(merged.assignments)) merged.assignments = [];
  if (!Array.isArray(merged.notes)) merged.notes = [];
  // Ensure every note has an images array (for older data)
  merged.notes.forEach(n => {
    if (!Array.isArray(n.images)) n.images = [];
  });
  return merged;
};

const subj = id => S.data.subjects.find(s => s.id === id) || { id: '', name: 'General', code: '', color: '#4F46E5', attended: 0, total: 0, credits: 3 };

/* ==========================================================================
   DYNAMIC RELATIVE SEED DATA
   ========================================================================== */
function seed() {
  const at = (daysOffset, h = 23, m = 59) => {
    const x = new Date();
    x.setDate(x.getDate() + daysOffset);
    x.setHours(h, m, 0, 0);
    return `${iso(x)}T${pad(h)}:${pad(m)}`;
  };
  const subjects = [
    { id: 's1', name: 'Data Structures & Algorithms', code: 'CS201', color: COLORS[0], attended: 28, total: 32, credits: 4 },
    { id: 's2', name: 'Database Management Systems', code: 'CS204', color: COLORS[1], attended: 22, total: 30, credits: 4 },
    { id: 's3', name: 'Operating Systems', code: 'CS206', color: COLORS[2], attended: 24, total: 31, credits: 4 },
    { id: 's4', name: 'Discrete Mathematics', code: 'MA201', color: COLORS[4], attended: 18, total: 20, credits: 3 },
    { id: 's5', name: 'Technical Communication', code: 'HS201', color: COLORS[5], attended: 12, total: 16, credits: 2 }
  ];
  const t = (id, subject, day, start, end, room) => ({ id, subject, day, start, end, room });
  const timetable = [
    t('t1','s1',0,'09:00','10:00','Room A-101'), t('t2','s2',0,'10:15','11:15','Room A-101'), t('t3','s4',0,'11:30','12:30','Hall B-202'),
    t('t4','s3',1,'09:00','10:00','Lab 3'), t('t5','s1',1,'10:15','11:15','Room A-101'), t('t6','s5',1,'14:00','15:00','Seminar Hall'),
    t('t7','s2',2,'09:00','11:00','DBMS Lab'), t('t8','s4',2,'11:30','12:30','Hall B-202'), t('t9','s3',2,'14:00','15:00','Room A-101'),
    t('t10','s1',3,'09:00','10:00','Room A-101'), t('t11','s3',3,'10:15','11:15','Lab 3'), t('t12','s5',3,'11:30','12:30','Seminar Hall'),
    t('t13','s4',4,'09:00','10:00','Hall B-202'), t('t14','s2',4,'10:15','11:15','Room A-101'), t('t15','s1',4,'11:30','12:30','Room A-101'),
    t('t16','s5',5,'10:00','11:00','Seminar Hall')
  ];
  const assignments = [
    { id: 'a1', title: 'DSA Lab 4: Graph BFS & DFS Traversal', subject: 's1', due: at(1, 22, 0), priority: 'high', done: false, details: 'Implement adjacency lists, BFS queue, and DFS recursion with benchmark tests.' },
    { id: 'a2', title: 'DBMS Case Study: Normalized Hospital Schema', subject: 's2', due: at(3, 23, 59), priority: 'med', done: false, details: 'Produce 3NF & BCNF ER schema documentation and SQL DDL tables.' },
    { id: 'a3', title: 'OS Project: Round Robin Scheduler Simulation', subject: 's3', due: at(5, 18, 0), priority: 'med', done: false, details: 'Write program simulating preemptive CPU round-robin scheduling.' },
    { id: 'a4', title: 'Maths Problem Set 4: Recurrence Relations', subject: 's4', due: at(-1, 23, 59), priority: 'high', done: false, details: 'Master theorem proofs and generating functions exercises.' },
    { id: 'a5', title: 'Technical Presentation Slides: Distributed Systems', subject: 's5', due: at(7, 12, 0), priority: 'low', done: false, details: 'Prepare 10 slides on Paxos vs Raft consensus.' }
  ];
  const notes = [
    { id: 'n1', title: 'Graph Traversal: BFS vs DFS', subject: 's1', pinned: true, updated: Date.now() - 3600000,
      body: 'Breadth-First Search (BFS): Explores level by level using a FIFO Queue. Optimal for finding the shortest path in unweighted graphs.\nDepth-First Search (DFS): Explores branch first using a LIFO Stack or recursion. Ideal for cycle detection and topological sorting.\nAdjacency List Time Complexity: O(V + E) for both algorithms.' },
    { id: 'n2', title: 'Database Normalization Essentials', subject: 's2', pinned: false, updated: Date.now() - 86400000,
      body: 'First Normal Form (1NF): Atomic values only, no repeating groups.\nSecond Normal Form (2NF): In 1NF and contains no partial functional dependency on composite candidate keys.\nThird Normal Form (3NF): In 2NF and contains zero transitive dependencies between non-key attributes.\nBCNF: Strict 3NF where every functional determinant X in X -> Y is a candidate key.' }
  ];
  const grades = [
    { id: 'g1', subject: 's1', credits: 4, grade: 'A' },
    { id: 'g2', subject: 's2', credits: 4, grade: 'A+' },
    { id: 'g3', subject: 's3', credits: 4, grade: 'A' },
    { id: 'g4', subject: 's4', credits: 3, grade: 'O' },
    { id: 'g5', subject: 's5', credits: 2, grade: 'A' }
  ];
  return Object.assign(emptyData(), { subjects, timetable, assignments, notes, grades });
}

/* ==========================================================================
   WMO WEATHER CODES MAP & COMPREHENSIVE WEATHER PARSER
   ========================================================================== */
const WMO_MAP = {
  0: { label: 'Clear Sky', icon: 'sun' },
  1: { label: 'Mainly Clear', icon: 'sun' },
  2: { label: 'Partly Cloudy', icon: 'cloud' },
  3: { label: 'Overcast', icon: 'cloud' },
  45: { label: 'Fog', icon: 'cloud' },
  48: { label: 'Depositing Rime Fog', icon: 'cloud' },
  51: { label: 'Light Drizzle', icon: 'rain' },
  53: { label: 'Moderate Drizzle', icon: 'rain' },
  55: { label: 'Dense Drizzle', icon: 'rain' },
  56: { label: 'Light Freezing Drizzle', icon: 'rain' },
  57: { label: 'Dense Freezing Drizzle', icon: 'rain' },
  61: { label: 'Slight Rain', icon: 'rain' },
  63: { label: 'Moderate Rain', icon: 'rain' },
  65: { label: 'Heavy Rain', icon: 'rain' },
  66: { label: 'Light Freezing Rain', icon: 'rain' },
  67: { label: 'Heavy Freezing Rain', icon: 'rain' },
  71: { label: 'Slight Snow Fall', icon: 'snow' },
  73: { label: 'Moderate Snow Fall', icon: 'snow' },
  75: { label: 'Heavy Snow Fall', icon: 'snow' },
  77: { label: 'Snow Grains', icon: 'snow' },
  80: { label: 'Slight Showers', icon: 'rain' },
  81: { label: 'Moderate Showers', icon: 'rain' },
  82: { label: 'Violent Showers', icon: 'rain' },
  85: { label: 'Slight Snow Showers', icon: 'snow' },
  86: { label: 'Heavy Snow Showers', icon: 'snow' },
  95: { label: 'Thunderstorm', icon: 'thunder' },
  96: { label: 'Thunderstorm with Slight Hail', icon: 'thunder' },
  99: { label: 'Thunderstorm with Heavy Hail', icon: 'thunder' }
};

const API = {
  async get(url, timeoutMs = 6000) {
    const ctrl = new AbortController();
    const timer = setTimeout(() => ctrl.abort(), timeoutMs);
    try {
      const r = await fetch(url, { signal: ctrl.signal, headers: { Accept: 'application/json' } });
      clearTimeout(timer);
      if (!r.ok) throw new Error(`HTTP ${r.status}`);
      return await r.json();
    } catch (e) {
      clearTimeout(timer);
      throw e;
    }
  },
  async weather(city) {
    const geo = await this.get(`https://geocoding-api.open-meteo.com/v1/search?name=${encodeURIComponent(city)}&count=1&language=en&format=json`);
    const p = geo.results && geo.results[0];
    if (!p) throw new Error('City not found');
    const w = await this.get(`https://api.open-meteo.com/v1/forecast?latitude=${p.latitude}&longitude=${p.longitude}&current=temperature_2m,weather_code,relative_humidity_2m,apparent_temperature&daily=temperature_2m_max,temperature_2m_min&timezone=auto`);
    const c = w.current || {};
    const meta = WMO_MAP[c.weather_code] || { label: 'Weather', icon: 'cloud' };
    return {
      city: p.name,
      country: p.country_code || '',
      temp: Math.round(c.temperature_2m),
      feel: Math.round(c.apparent_temperature),
      hum: c.relative_humidity_2m,
      code: c.weather_code,
      label: meta.label,
      iconName: meta.icon,
      hi: Math.round(w.daily.temperature_2m_max[0]),
      lo: Math.round(w.daily.temperature_2m_min[0])
    };
  },
  async quote() {
    try {
      const j = await this.get('https://dummyjson.com/quotes/random');
      return { text: j.quote, author: j.author };
    } catch (e) {
      return { text: 'Discipline is the bridge between goals and accomplishment.', author: 'Jim Rohn' };
    }
  },
  async holidays(year, cc = 'IN') {
    try {
      const j = await this.get(`https://date.nager.at/api/v3/PublicHolidays/${year}/${cc}`);
      if (Array.isArray(j) && j.length) return j;
    } catch (e) {}
    // Responsive dynamic festival fallback
    return [
      { date: `${year}-01-26`, localName: 'Republic Day', name: 'Republic Day' },
      { date: `${year}-08-15`, localName: 'Independence Day', name: 'Independence Day' },
      { date: `${year}-10-02`, localName: 'Gandhi Jayanti', name: 'Mahatma Gandhi Birthday' },
      { date: `${year}-12-25`, localName: 'Christmas Day', name: 'Christmas Day' }
    ];
  },
  async dict(word) {
    const cleanWord = word.trim().split(/\s+/)[0];
    const j = await this.get(`https://api.dictionaryapi.dev/api/v2/entries/en/${encodeURIComponent(cleanWord)}`);
    const e = j[0];
    const m = (e.meanings || [])[0];
    const defObj = (m && m.definitions && m.definitions[0]) || {};
    return {
      word: e.word,
      phonetic: e.phonetic || ((e.phonetics || []).find(x => x.text) || {}).text || '',
      part: (m && m.partOfSpeech) || 'noun',
      def: defObj.definition || 'Definition unavailable.',
      example: defObj.example || ''
    };
  },
  async wiki(q) {
    const j = await this.get(`https://en.wikipedia.org/api/rest_v1/page/summary/${encodeURIComponent(q.trim())}`);
    return {
      title: j.title || q,
      extract: j.extract || 'No article excerpt available.',
      url: j.content_urls && j.content_urls.desktop && j.content_urls.desktop.page
    };
  },
  async gemini(userText, key) {
    const url = 'https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent';
    
    // Build context-aware conversation history turns
    const contents = [
      {
        role: 'user',
        parts: [{ text: `You are Campus Desk, an intelligent and friendly college academic copilot for ${S.user.name.split(' ')[0]}.\nContext:\n${snapshot()}\n\nBe concise, helpful, and answer using plain text and simple markdown formatting.` }]
      },
      {
        role: 'model',
        parts: [{ text: `Hello! I have your complete timetable, attendance records, deadlines, and notes loaded. How can I help you today?` }]
      }
    ];

    // Include last recent conversation turns for context
    const recent = S.chat.slice(-6, -1);
    for (const m of recent) {
      if (m.text) {
        contents.push({
          role: m.role === 'assistant' ? 'model' : 'user',
          parts: [{ text: m.text }]
        });
      }
    }
    contents.push({ role: 'user', parts: [{ text: userText }] });

    const r = await fetch(url, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'x-goog-api-key': key
      },
      body: JSON.stringify({
        contents,
        generationConfig: {
          temperature: 0.6,
          maxOutputTokens: 2048
        }
      })
    });

    if (r.status === 400 || r.status === 403) {
      throw new Error('Invalid or unauthorized Gemini API key. Please check your key in Settings.');
    }
    if (r.status === 429) {
      throw new Error('Gemini API rate limit exceeded. Please wait a moment and try again.');
    }
    if (!r.ok) {
      throw new Error(`Gemini API Error (HTTP ${r.status})`);
    }

    const j = await r.json();
    const candidate = j.candidates && j.candidates[0];
    const text = candidate && candidate.content && candidate.content.parts && candidate.content.parts.map(p => p.text).join('');
    if (!text) throw new Error('Empty response from model.');
    return text;
  }
};

async function refreshCampus() {
  if (!S.user || !S.data) return;
  const city = (S.data.settings.city || 'Pune').trim();
  try {
    S.weather = await API.weather(city);
    S.apiOk.weather = true;
    store.set('cd:wx:' + city, S.weather);
  } catch (e) {
    S.weather = store.get('cd:wx:' + city, { city, country: '', temp: 26, feel: 27, hum: 55, label: 'Partly Cloudy', iconName: 'cloud', hi: 30, lo: 21 });
    S.apiOk.weather = false;
  }
  try {
    S.quote = await API.quote();
    S.apiOk.quote = true;
  } catch (e) { S.apiOk.quote = false; }
  try {
    const y = new Date().getFullYear();
    const h = await API.holidays(y);
    const today = iso(new Date());
    S.holidays = (h || []).filter(x => x.date >= today).slice(0, 6);
    S.apiOk.holidays = true;
  } catch (e) { S.apiOk.holidays = false; }
  
  if (S.view === 'home' || S.view === 'tools') render();
}

function applyTheme() {
  const t = (S.data && S.data.settings.theme) || store.get('cd:theme', 'system');
  if (t === 'dark' || t === 'light') {
    document.documentElement.setAttribute('data-theme', t);
  } else {
    document.documentElement.removeAttribute('data-theme');
  }
}

function toggleTheme() {
  const cur = (S.data && S.data.settings.theme) || 'system';
  let next = 'light';
  if (cur === 'system') {
    const isDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
    next = isDark ? 'light' : 'dark';
  } else if (cur === 'light') {
    next = 'dark';
  } else {
    next = 'light';
  }
  if (S.data) S.data.settings.theme = next;
  store.set('cd:theme', next);
  applyTheme();
  save();
  render();
  toast(`Theme switched to ${next} mode`);
}

function confetti() {
  const box = $('#confetti');
  if (!box) return;
  box.hidden = false;
  box.innerHTML = '';
  const cols = ['#4F46E5', '#10B981', '#F59E0B', '#EC4899', '#38BDF8', '#8B5CF6'];
  for (let i = 0; i < 32; i++) {
    const s = document.createElement('div');
    s.className = 'confetti-piece';
    s.style.left = (Math.random() * 100) + '%';
    s.style.backgroundColor = cols[i % cols.length];
    s.style.animationDelay = (Math.random() * 0.25) + 's';
    s.style.animationDuration = (0.9 + Math.random() * 0.5) + 's';
    box.appendChild(s);
  }
  setTimeout(() => { box.hidden = true; box.innerHTML = ''; }, 1600);
}

/* ==========================================================================
   ACADEMIC CALCULATIONS & BUNKING
   ========================================================================== */
const subjPct = s => s.total ? (s.attended / s.total) * 100 : 100;

const overall = () => {
  if (!S.data || !S.data.subjects.length) return 100;
  let a = 0, t = 0;
  S.data.subjects.forEach(s => { a += s.attended; t += s.total; });
  return t ? (a / t) * 100 : 100;
};

const stateOf = (p, target) => p < target ? 'bad' : p < (target + 5) ? 'warn' : 'ok';

function bunk(s, target) {
  const t = Math.min(Math.max(target, 50), 99) / 100;
  if (!s.total) return { ok: true, n: 0 };
  const currentRatio = s.attended / s.total;
  if (currentRatio >= t) {
    const n = Math.max(0, Math.floor((s.attended / t) - s.total + 1e-9));
    return { ok: true, n };
  } else {
    const n = Math.ceil(((t * s.total - s.attended) / (1 - t)) - 1e-9);
    return { ok: false, n: Math.max(1, n) };
  }
}

function verdict(s) {
  const t = (S.data && S.data.settings.target) || 75;
  const b = bunk(s, t);
  if (!s.total) return { k: 'ok', txt: 'No class attendance recorded yet.' };
  if (!b.ok) return { k: 'bad', txt: `Attend next ${b.n} ${plural(b.n, 'class', 'classes')} in a row to reach ${t}%.` };
  if (b.n === 0) return { k: 'warn', txt: `Caution: On the ${t}% threshold. Do not miss next class.` };
  return { k: b.n <= 1 ? 'warn' : 'ok', txt: `You can miss ${b.n} more ${plural(b.n, 'class', 'classes')} safely.` };
}

function nextClass() {
  if (!S.data || !S.data.timetable.length) return null;
  const now = new Date();
  const currentMin = now.getHours() * 60 + now.getMinutes();
  const todayDow = dow(now);

  for (let offset = 0; offset < 7; offset++) {
    const dayIndex = (todayDow + offset) % 7;
    const dayClasses = S.data.timetable.filter(x => x.day === dayIndex).sort(byStart);
    for (const it of dayClasses) {
      if (offset === 0) {
        if (toMin(it.end) <= currentMin) continue;
        if (toMin(it.start) <= currentMin) {
          return { it, label: `In progress until ${fmtT(it.end)}`, status: 'now', dayOffset: 0 };
        }
        return { it, label: `Today, ${fmtT(it.start)}`, status: 'today', dayOffset: 0 };
      }
      return {
        it,
        label: offset === 1 ? `Tomorrow, ${fmtT(it.start)}` : `${FULLDAYS[dayIndex]}, ${fmtT(it.start)}`,
        status: offset === 1 ? 'tomorrow' : 'future',
        dayOffset: offset
      };
    }
  }
  return null;
}

function nextClassEta() {
  const nx = nextClass();
  if (!nx) return 'No classes';
  if (nx.status === 'now') return 'In Progress';
  const now = new Date();
  const currentTotalSeconds = (now.getHours() * 3600) + (now.getMinutes() * 60) + now.getSeconds();
  const startTotalSeconds = toMin(nx.it.start) * 60;

  let diffSeconds = (nx.dayOffset * 86400) + (startTotalSeconds - currentTotalSeconds);
  // Guard against negative or huge values (e.g. day boundary edge cases)
  if (diffSeconds < 0) diffSeconds += 7 * 86400;
  if (diffSeconds > 7 * 86400) diffSeconds = diffSeconds % (7 * 86400);

  const hours = Math.floor(diffSeconds / 3600);
  const minutes = Math.floor((diffSeconds % 3600) / 60);
  const seconds = Math.floor(diffSeconds % 60);

  if (hours >= 24) return `${Math.round(hours / 24)} day${hours >= 48 ? 's' : ''}`;
  if (hours > 0) return `${hours}h ${minutes}m ${pad(seconds)}s`;
  return `${minutes}m ${pad(seconds)}s`;
}

let _notifCache = null;
let _notifCacheKey = '';
function notifs() {
  if (!S.data) return [];
  // Simple cache keyed by relevant data fingerprint
  const D = S.data;
  const key = D.assignments.map(a => a.id + a.done + a.due).join('|') + 
              D.subjects.map(s => s.id + s.attended + s.total).join('|') +
              (D.dismissed || []).join(',') + D.settings.target + D.settings.dueHours;
  if (_notifCache && _notifCacheKey === key) return _notifCache;
  _notifCacheKey = key;
  const now = Date.now(), out = [], t = D.settings.target;

  for (const a of D.assignments) {
    if (a.done) continue;
    const dueTime = new Date(a.due).getTime();
    if (isNaN(dueTime)) continue;
    const diff = dueTime - now;
    if (diff < 0) {
      out.push({ id: `over:${a.id}`, k: 'bad', rank: 0, title: `Overdue: ${a.title}`, body: `Was due ${fmtDue(a.due)}.`, go: 'tasks' });
    } else if (diff <= D.settings.dueHours * 3600e3) {
      out.push({ id: `due:${a.id}`, k: diff < 864e5 ? 'warn' : 'info', rank: diff < 864e5 ? 1 : 3, title: `Due ${rel(diff)}: ${a.title}`, body: `${subj(a.subject).name} · ${fmtDue(a.due)}`, go: 'tasks' });
    }
  }

  for (const s of D.subjects) {
    if (!s.total) continue;
    const b = bunk(s, t), p = Math.round(subjPct(s));
    if (!b.ok) {
      out.push({ id: `att:${s.id}:${p}`, k: 'bad', rank: 0, title: `Low Attendance: ${s.name} is ${p}%`, body: `Must attend next ${b.n} ${plural(b.n, 'class', 'classes')} to reach ${t}%.`, go: 'att' });
    } else if (b.n === 0) {
      out.push({ id: `att:${s.id}:${p}`, k: 'warn', rank: 2, title: `Attendance Warning: ${s.name} is ${p}%`, body: `On ${t}% cutoff. Do not miss next lecture.`, go: 'att' });
    }
  }

  const nx = nextClass();
  if (nx && nx.status === 'today') {
    const [h, m] = nx.it.start.split(':').map(Number);
    const startMin = h * 60 + m;
    const nowMin = new Date().getHours() * 60 + new Date().getMinutes();
    const diffMin = startMin - nowMin;
    if (diffMin > 0 && diffMin <= 30) {
      out.push({ id: `cls:${nx.it.id}:${iso(new Date())}`, k: 'info', rank: 1, title: `${subj(nx.it.subject).name} in ${diffMin} mins`, body: `${fmtT(nx.it.start)}${nx.it.room ? ' · ' + nx.it.room : ''}`, go: 'tt' });
    }
  }

  const dismissed = D.dismissed || [];
  _notifCache = out.filter(n => !dismissed.includes(n.id)).sort((a, b) => a.rank - b.rank);
  return _notifCache;
}

/* ==========================================================================
   FLASHCARDS FROM NOTES (BUG-FREE SEPARATOR PARSER)
   ========================================================================== */
function buildCards() {
  const out = [];
  if (S.data && S.data.notes) {
    for (const n of S.data.notes) {
      const lines = n.body.split(/\n+/).map(x => x.trim()).filter(Boolean);
      for (const line of lines) {
        // Split on genuine separator like "::" or ": " (colon followed by space).
        // NEVER split on "->" or periods inside sentences!
        const match = line.split(/\s*(?:::|:\s+)\s*/);
        if (match.length >= 2) {
          const q = match[0].replace(/^[-*•\d.]+\s*/, '').trim();
          const a = match.slice(1).join(': ').trim();
          if (q.length >= 2 && q.length <= 70 && a.length >= 4) {
            out.push({ q, a, from: n.title || 'Lecture Note' });
          }
        }
      }
    }
  }
  if (!out.length) {
    out.push({
      q: 'How do flashcards work?',
      a: 'Add notes with "Term: Definition" or "Concept :: Explanation" and tap Rebuild Deck!',
      from: 'Campus Desk Guide'
    });
  }
  S.cards = out;
  S.cardI = 0;
}

/* ==========================================================================
   LOCAL ASSISTANT (SEMANTIC WORD-BOUNDED NLP)
   ========================================================================== */
function snapshot() {
  const D = S.data, now = new Date(), t = D.settings.target;
  return JSON.stringify({
    currentTime: now.toLocaleString(),
    attendanceTarget: t,
    subjects: D.subjects.map(s => ({
      name: s.name,
      code: s.code,
      attendance: `${s.attended}/${s.total} (${Math.round(subjPct(s))}%)`,
      verdict: verdict(s).txt
    })),
    todayClasses: D.timetable.filter(x => x.day === dow(now)).sort(byStart).map(x => `${fmtT(x.start)}-${fmtT(x.end)}: ${subj(x.subject).name} (${x.room || 'No room'})`),
    pendingAssignments: D.assignments.filter(a => !a.done).map(a => ({ title: a.title, subject: subj(a.subject).name, due: fmtDue(a.due), priority: a.priority }))
  });
}

function localAnswer(q) {
  const text = q.trim();
  const lower = text.toLowerCase();
  const D = S.data;
  const now = new Date();

  // Check if student asked about a specific enrolled subject
  const matchedSubject = D.subjects.find(s =>
    new RegExp(`\\b${s.name.toLowerCase()}\\b`, 'i').test(lower) ||
    (s.code && new RegExp(`\\b${s.code.toLowerCase()}\\b`, 'i').test(lower))
  );

  if (matchedSubject) {
    const v = verdict(matchedSubject);
    const p = Math.round(subjPct(matchedSubject));
    const nextCls = D.timetable.filter(x => x.subject === matchedSubject.id).sort(byStart)[0];
    return `### ${matchedSubject.name} Status\n\n- **Attendance**: ${matchedSubject.attended}/${matchedSubject.total} classes (${p}%)\n- **Bunk Verdict**: ${v.txt}\n${nextCls ? `- **Next Class**: ${FULLDAYS[nextCls.day]} at ${fmtT(nextCls.start)}` : ''}`;
  }

  // Attendance queries with \b word boundaries
  if (/\b(attendance|bunk|bunking|miss|skip|percent|percentage|target)\b/i.test(lower)) {
    if (!D.subjects.length) return 'You have not added any subjects yet. Head to the **Attendance** tab to add your courses!';
    let rep = `### Attendance Overview (Target: ${D.settings.target}%)\n\n`;
    D.subjects.forEach(s => {
      rep += `- **${s.name}** (${Math.round(subjPct(s))}%): ${verdict(s).txt}\n`;
    });
    return rep;
  }

  // Schedule and timetable queries
  if (/\b(today|schedule|timetable|classes?|lectures?|now|next)\b/i.test(lower)) {
    const todayItems = D.timetable.filter(x => x.day === dow(now)).sort(byStart);
    if (!todayItems.length) return `You have **no lectures scheduled for today (${FULLDAYS[dow(now)]})**!`;
    let rep = `### Today's Schedule (${FULLDAYS[dow(now)]})\n\n`;
    todayItems.forEach(it => {
      rep += `- **${fmtT(it.start)} – ${fmtT(it.end)}**: ${subj(it.subject).name} *(${it.room || 'Room TBA'})*\n`;
    });
    return rep;
  }

  // Assignments queries
  if (/\b(assignment|assignments|tasks?|homework|deadlines?|due|submit)\b/i.test(lower)) {
    const pend = D.assignments.filter(a => !a.done).sort((a,b) => new Date(a.due) - new Date(b.due));
    if (!pend.length) return 'All caught up! You have **no pending assignments**. Great job!';
    let rep = `### Pending Assignments\n\n`;
    pend.forEach(a => {
      const isOver = new Date(a.due) < now;
      rep += `- **${a.title}** [${subj(a.subject).name}]: Due **${fmtDue(a.due)}** ${isOver ? '*(OVERDUE)*' : ''}\n`;
    });
    return rep;
  }

  // Weather query
  if (/\b(weather|temperature|forecast|rain|humidity|hot|cold)\b/i.test(lower) && S.weather) {
    const w = S.weather;
    return `### Campus Weather for ${w.city}\n\n- **Current**: ${w.temp}°C, ${w.label} (Feels like ${w.feel}°C)\n- **High / Low**: ${w.hi}°C / ${w.lo}°C\n- **Humidity**: ${w.hum}%`;
  }

  // GPA query
  if (/\b(gpa|cgpa|sgpa|grades?|credits?)\b/i.test(lower)) {
    let cr = 0, pt = 0;
    (D.grades || []).forEach(g => { const c = +g.credits || 0; cr += c; pt += c * (GRADE_PT[g.grade] || 0); });
    const gpa = cr ? (pt / cr).toFixed(2) : 'N/A';
    return `### Semester Academic Standing\n\nYour calculated SGPA is **${gpa}** across **${cr} credits**. You can adjust course grades under **Tools → GPA Calculator**.`;
  }

  // Notes content search in local assistant
  const matchedNote = D.notes.find(n =>
    new RegExp(`\\b${n.title.toLowerCase()}\\b`, 'i').test(lower) ||
    lower.includes(n.title.toLowerCase())
  );
  if (matchedNote) {
    return `### From Your Notes: ${matchedNote.title}\n\n${matchedNote.body.slice(0, 400)}${matchedNote.body.length > 400 ? '...' : ''}`;
  }

  return `I am your **Campus Desk Academic Copilot**. I can help you with:\n\n- **Timetable**: *"What do I have today?"*\n- **Attendance**: *"Can I bunk DBMS?"* or *"How is my attendance?"*\n- **Deadlines**: *"What assignments are due this week?"*\n- **Grades**: *"What is my GPA?"*\n\n*(Add your Gemini API Key in Settings for deep conceptual explanations!)*`;
}

async function sendChat(text) {
  text = (text || '').trim();
  if (!text || S.busy) return;

  const reply = { role: 'assistant', text: '' };
  S.chat.push({ role: 'user', text }, reply);
  S.busy = true;
  renderChat();

  const key = (S.data && S.data.settings && S.data.settings.geminiKey || '').trim();
  try {
    if (key) {
      reply.text = await API.gemini(text, key);
    } else {
      await new Promise(r => setTimeout(r, 350));
      reply.text = localAnswer(text);
    }
  } catch (err) {
    reply.text = `${localAnswer(text)}\n\n*(Notice: ${err.message || 'Gemini API unavailable'})*`;
  }

  S.busy = false;
  store.set('cd:chat:' + S.user.id, S.chat.slice(-30));
  renderChat();
}

/* ==========================================================================
   MARKDOWN PARSER
   ========================================================================== */
function md(t) {
  if (!t) return '';
  // Basic sanitization against script injection
  t = String(t).replace(/<(script|style|iframe|object|embed|link|meta)[^>]*>[\s\S]*?<\/\1>/gi, '')
               .replace(/\bon\w+\s*=\s*("[^"]*"|'[^']*'|[^\s>]+)/gi, '');
  // Code block fences
  t = t.replace(/```(?:(\w+)?\n)?([\s\S]*?)```/g, (_, lang, code) => {
    return `\n<pre class="code-block"><code>${esc(code.trim())}</code></pre>\n`;
  });

  const lines = t.split('\n');
  let out = '';
  let inUl = false, inOl = false;

  const formatInline = s => {
    // Escape first for safety, then apply markdown
    let safe = esc(s);
    return safe
      .replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>')
      .replace(/\*(.+?)\*/g, '<em>$1</em>')
      .replace(/\_(.+?)\_/g, '<em>$1</em>')
      .replace(/`(.+?)`/g, '<code>$1</code>');
  };

  for (const raw of lines) {
    if (raw.startsWith('<pre class="code-block">')) {
      if (inUl) { out += '</ul>'; inUl = false; }
      if (inOl) { out += '</ol>'; inOl = false; }
      out += raw;
      continue;
    }

    // Numbered list
    const olMatch = raw.match(/^\s*(\d+)[.)]\s+(.*)$/);
    if (olMatch) {
      if (inUl) { out += '</ul>'; inUl = false; }
      if (!inOl) { out += '<ol>'; inOl = true; }
      out += `<li>${formatInline(olMatch[2])}</li>`;
      continue;
    }

    // Bulleted list
    const ulMatch = raw.match(/^\s*[-*•]\s+(.*)$/);
    if (ulMatch) {
      if (inOl) { out += '</ol>'; inOl = false; }
      if (!inUl) { out += '<ul>'; inUl = true; }
      out += `<li>${formatInline(ulMatch[1])}</li>`;
      continue;
    }

    if (inUl) { out += '</ul>'; inUl = false; }
    if (inOl) { out += '</ol>'; inOl = false; }

    const trimmed = raw.trim();
    if (!trimmed) continue;

    const h = raw.match(/^#{1,6}\s+(.*)$/);
    if (h) {
      out += `<p style="font-weight:700;margin-top:6px"><strong>${formatInline(h[1])}</strong></p>`;
    } else {
      out += `<p>${formatInline(raw)}</p>`;
    }
  }

  if (inUl) out += '</ul>';
  if (inOl) out += '</ol>';
  return out;
}

/* ==========================================================================
   AUTHENTICATION & STORAGE SYNC
   ========================================================================== */
async function hash(pw, salt) {
  // Prefer Web Crypto SHA-256. Fallback is intentionally weak and only for very old browsers.
  try {
    if (!crypto || !crypto.subtle) throw new Error('Web Crypto unavailable');
    const b = new TextEncoder().encode(salt + ':' + pw);
    const d = await crypto.subtle.digest('SHA-256', b);
    return Array.from(new Uint8Array(d)).map(x => x.toString(16).padStart(2, '0')).join('');
  } catch (e) {
    console.warn('Falling back to simple hash – upgrade browser for stronger protection');
    let h = 0;
    for (const c of (salt + pw)) h = (h * 31 + c.charCodeAt(0)) | 0;
    return 'h_' + h;
  }
}

function login(u) {
  S.user = u;
  S.data = loadData(u.id);
  S.chat = store.get('cd:chat:' + u.id, []);
  S.view = 'home';
  S.noteId = null;
  store.set('cd:session', u.id);
  // Sync custom timer from settings
  const st = S.data.settings || {};
  S.pomo.customFocus = Math.max(1, Math.min(180, +(st.focusMin || 25)));
  S.pomo.customBreak = Math.max(1, Math.min(60, +(st.breakMin || 5)));
  if (!S.pomo.run) {
    S.pomo.left = S.pomo.customFocus * 60;
    S.pomo.mode = 'focus';
  }
  applyTheme();
  render();
  window.scrollTo(0, 0);
  refreshCampus();
  buildCards();
}

function logout() {
  store.set('cd:session', null);
  S.user = null;
  S.data = null;
  S.chat = [];
  S.authTab = 'in';
  render();
}

/* ---- Security question (password recovery) ---- */
const SEC_QUESTIONS = [
  "What was the name of your first pet?",
  "What was the name of your first school?",
  "In which city or village were you born?",
  "What was your childhood nickname?",
  "Who was your favourite teacher?",
  "What was the first movie you watched in a theatre?",
  "What is the name of your best childhood friend?"
];
const normAns = s => String(s || '').toLowerCase().replace(/\s+/g, ' ').trim();

function secFields() {
  return `
    <div class="form-field">
      <label for="sq_q">Security Question</label>
      <select id="sq_q" name="secQ">${SEC_QUESTIONS.map(q => `<option value="${esc(q)}">${esc(q)}</option>`).join('')}</select>
    </div>
    <div class="form-field">
      <label for="sq_c">…or write your own question (optional)</label>
      <input id="sq_c" name="customQ" maxlength="120" placeholder="Something only you would know" autocomplete="off">
    </div>
    <div class="form-field">
      <label for="sq_a">Your Answer</label>
      <input id="sq_a" name="secA" maxlength="80" autocomplete="off" required>
      <span class="mut xs">Not case-sensitive. Choose something others can't easily guess.</span>
    </div>`;
}

function validateSq(fd) {
  const custom = (fd.customQ || '').trim();
  if (custom && custom.length < 8) return 'Your own security question should be at least 8 characters.';
  if (normAns(fd.secA).length < 3) return 'Security answer must be at least 3 characters.';
  return '';
}

async function makeSq(fd) {
  const q = (fd.customQ || '').trim() || fd.secQ;
  const salt = uid();
  return { q, salt, hash: await hash(normAns(fd.secA), salt), fails: 0, lockUntil: 0 };
}

async function doReset(f, err) {
  const fd = Object.fromEntries(new FormData(f));
  const users = getUsers();
  const R = S.reset || { step: 1 };

  if (R.step === 1) {
    const email = (fd.email || '').trim().toLowerCase();
    if (!email) { err.textContent = 'Please enter your email or roll number.'; return; }
    const u = users.find(x => x.email === email);
    if (!u) { err.textContent = 'No account found with those details.'; return; }
    if (!u.sq) {
      err.textContent = 'This account has no security question set, so its password cannot be reset here.';
      return;
    }
    S.reset = { step: 2, email, question: u.sq.q };
    render();
    return;
  }

  const u = users.find(x => x.email === R.email);
  if (!u || !u.sq) { err.textContent = 'Account not found. Please start again.'; return; }

  const wait = (u.sq.lockUntil || 0) - Date.now();
  if (wait > 0) {
    err.textContent = `Too many wrong answers. Try again in ${Math.ceil(wait / 60000)} min.`;
    return;
  }

  const pw = fd.password || '', pw2 = fd.password2 || '';
  if (!normAns(fd.secA)) { err.textContent = 'Please answer your security question.'; return; }
  if (pw.length < 5) { err.textContent = 'New password must be at least 5 characters.'; return; }
  if (pw !== pw2) { err.textContent = 'The two passwords do not match.'; return; }

  if ((await hash(normAns(fd.secA), u.sq.salt)) !== u.sq.hash) {
    u.sq.fails = (u.sq.fails || 0) + 1;
    let msg = 'Incorrect answer.';
    if (u.sq.fails >= 5) {
      u.sq.fails = 0;
      u.sq.lockUntil = Date.now() + 5 * 60000;
      msg = 'Too many wrong answers. Locked for 5 minutes.';
    }
    store.set('cd:users', users);
    err.textContent = msg;
    return;
  }

  u.salt = uid();
  u.hash = await hash(pw, u.salt);
  u.sq.fails = 0;
  u.sq.lockUntil = 0;
  store.set('cd:users', users);
  S.reset = null;
  S.authTab = 'in';
  render();
  toast('Password updated. Please sign in.');
}

function secQuestionModal() {
  const cur = getUsers().find(u => u.id === S.user.id);
  openModal(
    'Security Question',
    `
      <p class="mut sm">${cur && cur.sq
        ? 'Current question: <b>' + esc(cur.sq.q) + '</b>. Saving below replaces it.'
        : 'Set a question so you can reset your password if you ever forget it.'}</p>
      ${secFields()}
      <div class="form-field">
        <label for="sq_pw">Current Password</label>
        <input id="sq_pw" name="curpw" type="password" required autocomplete="current-password">
      </div>
    `,
    async fd => {
      const users = getUsers();
      const u = users.find(x => x.id === S.user.id);
      if (!u) return 'Account not found.';
      if ((await hash(fd.curpw || '', u.salt)) !== u.hash) return 'Current password is incorrect.';
      const e = validateSq(fd);
      if (e) return e;
      u.sq = await makeSq(fd);
      store.set('cd:users', users);
      toast('Security question saved.');
    },
    null,
    'Save Question'
  );
}

async function doAuth() {
  const f = $('#authform'), err = $('#autherr');
  err.textContent = '';
  if (S.authTab === 'reset') return doReset(f, err);
  const fd = Object.fromEntries(new FormData(f));
  const email = (fd.email || '').trim().toLowerCase(), pw = fd.password || '', name = (fd.name || '').trim();

  if (!email || !pw) {
    err.textContent = 'Please provide your email/roll number and password.';
    return;
  }

  const users = getUsers();
  if (S.authTab === 'up') {
    if (!name) { err.textContent = 'Please enter your full name.'; return; }
    if (pw.length < 5) { err.textContent = 'Password must be at least 5 characters.'; return; }
    if (users.some(u => u.email === email)) { err.textContent = 'Account already exists. Please sign in instead.'; return; }
    const sqErr = validateSq(fd);
    if (sqErr) { err.textContent = sqErr; return; }
    const salt = uid();
    const u = { id: uid(), name, email, salt, hash: await hash(pw, salt), sq: await makeSq(fd) };
    users.push(u);
    store.set('cd:users', users);
    store.set('cd:data:' + u.id, emptyData());
    login(u);
  } else {
    const u = users.find(x => x.email === email);
    if (!u || (await hash(pw, u.salt)) !== u.hash) {
      err.textContent = 'Incorrect credentials. Please verify your details.';
      return;
    }
    login(u);
  }
}

async function demo() {
  const email = 'alex@campus.edu';
  const users = getUsers();
  let u = users.find(x => x.email === email);
  if (!u) {
    const salt = uid();
    u = { id: uid(), name: 'Alex Johnson', email, salt, hash: await hash('demo123', salt) };
    users.push(u);
    store.set('cd:users', users);
    store.set('cd:data:' + u.id, seed());
  }
  login(u);
}

// Multi-tab synchronization
window.addEventListener('storage', e => {
  if (e.key && e.key.startsWith('cd:') && S.user) {
    if (e.key === 'cd:session' && !e.newValue) {
      logout();
      return;
    }
    if (e.key === 'cd:data:' + S.user.id) {
      S.data = loadData(S.user.id);
      render();
    }
  }
});

/* ==========================================================================
   RENDER VIEWS
   ========================================================================== */
const NAV = [
  ['home', 'Dashboard', 'home'],
  ['tt', 'Timetable', 'calendar'],
  ['att', 'Attendance', 'check'],
  ['tasks', 'Assignments', 'tasks'],
  ['notes', 'Notes & AI', 'notes'],
  ['chat', 'Ask AI', 'chat'],
  ['tools', 'Tools', 'spark'],
  ['alerts', 'Notifications', 'bell']
];

function render() {
  const app = $('#app');
  if (!S.user) {
    app.innerHTML = authView();
    return;
  }

  const notifCount = notifs().length;
  const sideNavHtml = NAV.map(([k, l, ic]) => `
    <button class="nav-item ${S.view === k ? 'active' : ''}" data-act="nav" data-v="${k}" aria-current="${S.view === k ? 'page' : 'false'}">
      ${icon(ic, 19)}
      <span>${l}</span>
      ${k === 'alerts' && notifCount ? `<span class="nav-badge ${notifCount > 3 ? 'bad' : ''}">${notifCount}</span>` : ''}
    </button>
  `).join('');

  // Mobile Bottom Navigation: EXACTLY 5 TABS (Today, Timetable, Attendance, Tasks, More)
  const mobileTabsHtml = `
    <button class="tab-btn ${S.view === 'home' ? 'active' : ''}" data-act="nav" data-v="home">
      ${icon('home', 19)}
      <span>Today</span>
    </button>
    <button class="tab-btn ${S.view === 'tt' ? 'active' : ''}" data-act="nav" data-v="tt">
      ${icon('calendar', 19)}
      <span>Schedule</span>
    </button>
    <button class="tab-btn ${S.view === 'att' ? 'active' : ''}" data-act="nav" data-v="att">
      ${icon('check', 19)}
      <span>Attendance</span>
    </button>
    <button class="tab-btn ${S.view === 'tasks' ? 'active' : ''}" data-act="nav" data-v="tasks">
      ${icon('tasks', 19)}
      <span>Tasks</span>
    </button>
    <button class="tab-btn ${['notes','chat','tools','alerts'].includes(S.view) ? 'active' : ''}" data-act="more-open">
      ${icon('more', 19)}
      <span>More</span>
    </button>
  `;

  app.innerHTML = `
    <div class="shell">
      <!-- Desktop Sidebar -->
      <aside class="side">
        <div class="brand">
          <div class="brand-icon-box">${icon('calendar', 20)}</div>
          <div class="brand-title">
            Campus Desk
            <span>College Copilot</span>
          </div>
        </div>

        <button class="cmd-btn" data-act="cmd-open">
          <div style="display:flex;align-items:center;gap:8px">
            ${icon('search', 16)}
            <span>Search...</span>
          </div>
          <span class="kbd-pill">${cmdKeyText}</span>
        </button>

        <nav class="nav-group">
          ${sideNavHtml}
        </nav>

        <div class="side-footer">
          <button class="user-card" data-act="profile">
            <div class="avatar">${esc(S.user.name.charAt(0).toUpperCase())}</div>
            <div class="user-info grow">
              <div class="user-name truncate">${esc(S.user.name)}</div>
              <div class="user-role truncate">${esc(S.user.email)}</div>
            </div>
            ${icon('settings', 16)}
          </button>
          <div style="display:flex;gap:6px">
            <button class="btn ghost sm grow" data-act="theme-toggle">${icon('sun', 15)}Theme</button>
            <button class="btn ghost sm danger" data-act="logout">Sign out</button>
          </div>
        </div>
      </aside>

      <!-- Main Column -->
      <div class="main-wrapper">
        <!-- Mobile Top Bar -->
        <header class="mobile-top">
          <div class="brand">
            <div class="brand-icon-box" style="width:30px;height:30px">${icon('calendar', 16)}</div>
            <span style="font-size:16.5px;font-weight:700">Campus Desk</span>
          </div>
          <div style="display:flex;align-items:center;gap:8px">
            <button class="icon-btn" data-act="cmd-open" aria-label="Search">${icon('search', 17)}</button>
            <button class="icon-btn" data-act="nav" data-v="alerts" aria-label="Notifications" style="position:relative">
              ${icon('bell', 17)}
              ${notifCount ? `<span class="nav-badge bad" style="position:absolute;top:-4px;right:-4px;padding:2px 5px;font-size:10px">${notifCount}</span>` : ''}
            </button>
            <button class="icon-btn" data-act="profile" aria-label="Settings">${icon('settings', 17)}</button>
          </div>
        </header>

        <!-- View Body -->
        <main class="content-container" id="main">
          ${view()}
        </main>
      </div>

      <!-- Mobile Bottom Navigation -->
      <nav class="mobile-tabs" aria-label="Bottom Navigation">
        ${mobileTabsHtml}
      </nav>
    </div>
  `;

  if (S.view === 'chat') {
    const l = $('#chatlog');
    if (l) l.scrollTop = l.scrollHeight;
  }
}

function view() {
  switch (S.view) {
    case 'tt': return ttView();
    case 'att': return attView();
    case 'tasks': return tasksView();
    case 'notes': return notesView();
    case 'chat': return chatView();
    case 'tools': return toolsView();
    case 'alerts': return alertsView();
    default: return homeView();
  }
}

/* ==========================================================================
   VIEW: AUTH
   ========================================================================== */
function authView() {
  const rs = S.authTab === 'reset';
  const rstep = rs && S.reset ? S.reset.step : 1;
  const up = S.authTab === 'up';
  return `
    <div style="min-height:100vh;min-height:100dvh;display:grid;place-items:center;padding:20px;background:radial-gradient(ellipse at top, var(--brand-subtle), var(--bg))">
      <div style="width:min(940px,100%);display:grid;grid-template-columns:repeat(auto-fit, minmax(300px, 1fr));border:1px solid var(--line);border-radius:var(--radius-xl);overflow:hidden;background:var(--surface);box-shadow:var(--shadow-xl)">
        
        <div style="background:linear-gradient(135deg, #1E1B4B, #312E81);color:#FFF;padding:40px 32px;display:flex;flex-direction:column;justify-content:space-between;gap:28px">
          <div>
            <div style="display:flex;align-items:center;gap:12px;margin-bottom:24px">
              <div class="brand-icon-box" style="background:#FFF;color:#1E1B4B">${icon('calendar', 20)}</div>
              <h2 style="font-size:21px;color:#FFF">Campus Desk</h2>
            </div>
            <h1 style="font-size:32px;color:#FFF;line-height:1.2;margin-bottom:12px">Your Academic Command Center.</h1>
            <p style="color:rgba(255,255,255,0.85);font-size:14.5px;line-height:1.5">Track attendance, calculate safe bunks, organize lecture notes, and get instant answers from your campus AI copilot.</p>
          </div>
          <div style="display:flex;flex-direction:column;gap:12px">
            <div style="display:flex;align-items:center;gap:10px;font-size:13.5px;color:rgba(255,255,255,0.9)">${icon('check', 17)} Safe bunk formulas and target tracking</div>
            <div style="display:flex;align-items:center;gap:10px;font-size:13.5px;color:rgba(255,255,255,0.9)">${icon('calendar', 17)} Lecture timetable with live class alerts</div>
            <div style="display:flex;align-items:center;gap:10px;font-size:13.5px;color:rgba(255,255,255,0.9)">${icon('spark', 17)} Gemini AI and local offline assistant</div>
          </div>
        </div>

        <form id="authform" style="padding:40px 34px;display:flex;flex-direction:column;justify-content:center;gap:16px" autocomplete="on">
          <div>
            <h2>${rs ? 'Reset Password' : up ? 'Create Account' : 'Sign In'}</h2>
            <p class="mut sm" style="margin-top:4px">${rs
              ? (rstep === 2 ? 'Answer your security question, then choose a new password.' : 'Enter your email or roll number to find your account.')
              : "All records are stored privately in your browser's local storage."}</p>
          </div>

          ${rs ? '' : `
          <div class="segmented" style="align-self:flex-start">
            <button type="button" class="seg-btn ${up ? '' : 'active'}" data-act="auth-tab" data-t="in">Sign In</button>
            <button type="button" class="seg-btn ${up ? 'active' : ''}" data-act="auth-tab" data-t="up">Register</button>
          </div>`}

          ${up ? `
            <div class="form-field">
              <label for="an">Full Name</label>
              <input id="an" name="name" placeholder="e.g. Alex Johnson" required autocomplete="name">
            </div>
          ` : ''}

          ${rs && rstep === 2 ? `
            <div class="form-field">
              <label for="rq">Security Question</label>
              <p id="rq" style="font-weight:600;margin:0">${esc(S.reset.question)}</p>
            </div>
            <div class="form-field">
              <label for="ra">Your Answer</label>
              <input id="ra" name="secA" autocomplete="off" required>
            </div>
            <div class="form-field">
              <label for="rp1">New Password</label>
              <input id="rp1" name="password" type="password" placeholder="••••••••" required autocomplete="new-password">
            </div>
            <div class="form-field">
              <label for="rp2">Confirm New Password</label>
              <input id="rp2" name="password2" type="password" placeholder="••••••••" required autocomplete="new-password">
            </div>
          ` : `
            <div class="form-field">
              <label for="ae">College Email or Roll Number</label>
              <input id="ae" name="email" placeholder="student@college.edu" required autocomplete="username">
            </div>
          `}

          ${rs ? '' : `
          <div class="form-field">
            <label for="ap">Password</label>
            <input id="ap" name="password" type="password" placeholder="••••••••" required autocomplete="${up ? 'new-password' : 'current-password'}">
          </div>`}

          ${!rs && !up ? `
            <button type="button" data-act="auth-forgot" style="background:none;border:0;padding:0;margin-top:-6px;align-self:flex-end;color:var(--brand);font-size:13px;font-weight:600;cursor:pointer">Forgot password?</button>
          ` : ''}

          ${up ? secFields() : ''}

          <p id="autherr" style="color:var(--bad);font-size:13px;font-weight:500;margin:0" role="alert"></p>

          <button class="btn primary" type="submit" style="width:100%;padding:11px">${rs ? (rstep === 2 ? 'Reset Password' : 'Continue') : up ? 'Create Account' : 'Sign In'}</button>

          ${rs ? `
            <button class="btn ghost" type="button" data-act="auth-back" style="width:100%">← Back to Sign In</button>
          ` : `
            <button class="btn ghost" type="button" data-act="demo" style="width:100%">
              ⚡ Explore with Realistic Demo Courses
            </button>
          `}
        </form>

      </div>
    </div>
  `;
}

/* ==========================================================================
   VIEW: DASHBOARD
   ========================================================================== */
function homeView() {
  const D = S.data, now = new Date();
  const first = S.user.name.split(' ')[0];
  const greeting = now.getHours() < 12 ? 'Good morning' : now.getHours() < 17 ? 'Good afternoon' : 'Good evening';
  const dateStr = now.toLocaleDateString(undefined, { weekday: 'long', month: 'long', day: 'numeric' });

  if (!D.subjects.length) {
    return `
      <div class="page-header">
        <div>
          <h1 class="page-title">${greeting}, ${esc(first)}</h1>
          <p class="page-sub">${dateStr} · Welcome to Campus Desk</p>
        </div>
      </div>
      <div class="card" style="text-align:center;padding:44px 20px">
        <h2>Let's configure your semester</h2>
        <p class="mut sm" style="max-width:440px;margin:8px auto 20px">Add your enrolled subjects to enable attendance calculations, safe bunks, and timetable alerts.</p>
        <div style="display:flex;justify-content:center;gap:10px">
          <button class="btn primary" data-act="sub-add">${icon('plus')} Add Subject</button>
          <button class="btn" data-act="load-sample">⚡ Load Demo Schedule</button>
        </div>
      </div>
    `;
  }

  const nx = nextClass();
  let heroCardHtml = '';

  if (nx) {
    const isTodayOrNow = (nx.status === 'now' || nx.status === 'today');
    const markKey = nx.it.id + '|' + iso(now);
    const isMarkedP = D.marks[markKey] === 'P';

    heroCardHtml = `
      <div class="hero-card" id="hero-card">
        <div>
          <div class="hero-tag">
            ${icon('clock', 14)}
            <span id="hero-tag-lbl">${esc(nx.label)}</span>
          </div>
          <div class="hero-subject">${esc(subj(nx.it.subject).name)}</div>
          <div class="hero-meta">
            <span class="hero-meta-item">${icon('calendar', 16)} ${fmtT(nx.it.start)} – ${fmtT(nx.it.end)}</span>
            ${nx.it.room ? `<span class="hero-meta-item">${icon('home', 16)} ${esc(nx.it.room)}</span>` : ''}
            <span class="hero-meta-item">${icon('spark', 16)} Code: ${esc(subj(nx.it.subject).code || 'CS')}</span>
          </div>
        </div>
        <div style="display:flex;align-items:center;gap:10px;margin-top:18px;flex-wrap:wrap">
          ${isTodayOrNow ? `
            <button class="btn sm hero-mark-btn ${isMarkedP ? 'marked' : ''}" data-act="mark-hero" data-id="${nx.it.id}">
              ${isMarkedP ? `${icon('tick', 15)} Marked Present` : `${icon('plus', 15)} Mark Present`}
            </button>
          ` : `
            <span class="badge" style="background:rgba(255,255,255,0.18);color:#FFF;border-color:transparent">
              ${nx.status === 'tomorrow' ? 'Starts Tomorrow' : `Starts ${FULLDAYS[nx.it.day]}`}
            </span>
          `}
          <button class="btn sm ghost" data-act="nav" data-v="tt" style="color:#FFF;border-color:rgba(255,255,255,0.3)">View Timetable</button>
        </div>
      </div>
    `;
  } else {
    heroCardHtml = `
      <div class="hero-card" style="background:linear-gradient(135deg, #0F172A, #1E293B)">
        <div>
          <div class="hero-tag">${icon('check', 14)} Free Block</div>
          <div class="hero-subject">No More Lectures Today</div>
          <p style="color:rgba(255,255,255,0.8);margin-top:8px;font-size:13.5px">All classes completed. Check your assignments or review your lecture notes.</p>
        </div>
        <div style="margin-top:18px">
          <button class="btn sm" data-act="nav" data-v="notes" style="background:#FFF;color:#0F172A">${icon('notes', 16)} Open Notes</button>
        </div>
      </div>
    `;
  }

  // Attendance Standing calculations
  const ov = overall(), target = D.settings.target;
  const ovState = stateOf(ov, target);
  const circ = 2 * Math.PI * 38;
  const strokeDash = `${(circ * Math.min(ov, 100) / 100).toFixed(1)} ${circ.toFixed(1)}`;
  
  // Differentiate truly critical (< target) vs cautionary (within 5%)
  const criticalSubj = D.subjects.filter(s => s.total && (subjPct(s) < target)).sort((a,b) => subjPct(a) - subjPct(b));
  const warningSubj = D.subjects.filter(s => s.total && (subjPct(s) >= target && subjPct(s) < target + 5)).sort((a,b) => subjPct(a) - subjPct(b));

  const attCardHtml = `
    <div class="card">
      <div class="card-head">
        <h3>Attendance Standing</h3>
        <button class="btn sm ghost" data-act="nav" data-v="att">Manage</button>
      </div>
      <div class="att-snap-grid">
        <div class="ring-wrap">
          <svg class="ring-svg" width="90" height="90" viewBox="0 0 100 100">
            <circle class="ring-bg" cx="50" cy="50" r="38" fill="none" stroke-width="8"/>
            <circle class="ring-fg" cx="50" cy="50" r="38" fill="none" stroke="var(--${ovState})" stroke-width="8" stroke-dasharray="${strokeDash}"/>
          </svg>
          <div class="ring-center">
            <span class="ring-pct">${Math.round(ov)}%</span>
            <span class="ring-lbl">Overall</span>
          </div>
        </div>
        <div class="grow">
          ${criticalSubj.length ? `
            <div style="font-size:13px;font-weight:700;color:var(--bad);margin-bottom:3px">⚠️ Low Attendance Alert</div>
            <div style="font-size:12.5px;color:var(--ink-secondary);line-height:1.4">
              <b>${esc(criticalSubj[0].name)}</b> is at <b>${Math.round(subjPct(criticalSubj[0]))}%</b>.
              <span class="mut">${esc(verdict(criticalSubj[0]).txt)}</span>
            </div>
          ` : warningSubj.length ? `
            <div style="font-size:13px;font-weight:700;color:var(--warn);margin-bottom:3px">⚠️ Approaching Cutoff (${warningSubj[0].name})</div>
            <div style="font-size:12.5px;color:var(--ink-secondary);line-height:1.4">
              Currently at <b>${Math.round(subjPct(warningSubj[0]))}%</b>. One missed class will drop below ${target}%.
            </div>
          ` : `
            <div style="font-size:13px;font-weight:700;color:var(--ok);margin-bottom:3px">✓ Healthy Standing</div>
            <div class="mut sm">All subjects are comfortably above your <b>${target}%</b> target.</div>
          `}
        </div>
      </div>
    </div>
  `;

  // Today's classes
  const todayClasses = D.timetable.filter(x => x.day === dow(now)).sort(byStart);
  const classRowsHtml = todayClasses.map(it => {
    const s = subj(it.subject);
    const markKey = it.id + '|' + iso(now);
    const curMark = D.marks[markKey];
    return `
      <div class="class-row">
        <div class="class-color-bar" style="--c:${esc(s.color)}"></div>
        <div class="grow">
          <div class="class-title">${esc(s.name)}</div>
          <div class="class-sub">${fmtT(it.start)} – ${fmtT(it.end)} ${it.room ? '· ' + esc(it.room) : ''}</div>
        </div>
        <div class="segmented">
          <button class="seg-btn ${curMark === 'P' ? 'active ok' : ''}" data-act="mark" data-id="${esc(it.id)}" data-s="P" aria-pressed="${curMark === 'P'}">Present</button>
          <button class="seg-btn ${curMark === 'A' ? 'active bad' : ''}" data-act="mark" data-id="${esc(it.id)}" data-s="A" aria-pressed="${curMark === 'A'}">Absent</button>
        </div>
      </div>
    `;
  }).join('') || `<p class="mut sm" style="padding:14px 0">No classes scheduled for today.</p>`;

  // Pending Tasks
  const pendingTasks = D.assignments.filter(a => !a.done).sort((a,b) => new Date(a.due) - new Date(b.due)).slice(0, 4);
  const taskRowsHtml = pendingTasks.map(a => {
    const diff = new Date(a.due).getTime() - now.getTime();
    const isOver = diff < 0;
    return `
      <div class="task-row">
        <button class="task-check" data-act="as-toggle" data-id="${esc(a.id)}" aria-label="Mark completed">${icon('tick', 13)}</button>
        <div class="grow">
          <div class="task-title">${esc(a.title)}</div>
          <div class="task-meta">
            <span class="badge sm" style="background:var(--bg-subtle)"><i class="badge-dot" style="color:${esc(subj(a.subject).color)}"></i> ${esc(subj(a.subject).name)}</span>
            <span class="${isOver ? 'badge sm bad' : 'mut'}">${isOver ? 'Overdue: ' + fmtDue(a.due) : 'Due ' + rel(diff)}</span>
          </div>
        </div>
      </div>
    `;
  }).join('') || `<p class="mut sm" style="padding:14px 0">Zero pending assignments. Great job!</p>`;

  // Campus Ticker
  const wx = S.weather;
  const tickerHtml = `
    <div class="campus-ticker">
      <div class="ticker-pill">
        <span class="live-dot"></span>
        <span>Clock: <b id="liveclock">${now.toLocaleTimeString([], { hour:'numeric', minute:'2-digit', second:'2-digit' })}</b></span>
      </div>
      <div class="ticker-pill">
        ${icon('clock', 15)}
        <span>Class Countdown: <b id="liveeta" style="color:var(--brand)">${nextClassEta()}</b></span>
      </div>
      ${wx ? `
        <div class="ticker-pill">
          ${icon(wx.iconName || 'sun', 15)}
          <span>${esc(wx.city)}: <b>${wx.temp}°C, ${esc(wx.label)}</b></span>
        </div>
      ` : ''}
      ${(S.holidays || [])[0] ? `
        <div class="ticker-pill">
          ${icon('calendar', 15)}
          <span>Next Holiday: <b>${esc(S.holidays[0].localName)}</b> (${esc(S.holidays[0].date)})</span>
        </div>
      ` : ''}
    </div>
  `;

  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">${greeting}, ${esc(first)}</h1>
        <p class="page-sub">${dateStr}</p>
      </div>
      <div class="actions-row">
        <button class="btn primary" data-act="as-add">${icon('plus')} Add Task</button>
        <button class="btn" data-act="cmd-open">${icon('search')} Jump Anywhere</button>
      </div>
    </div>

    ${tickerHtml}

    <div class="grid g2" style="margin-bottom:18px">
      ${heroCardHtml}
      ${attCardHtml}
    </div>

    <div class="grid g2">
      <div class="card">
        <div class="card-head">
          <h3>Today's Classes</h3>
          <button class="btn sm ghost" data-act="nav" data-v="tt">Full Schedule</button>
        </div>
        ${classRowsHtml}
      </div>

      <div class="card">
        <div class="card-head">
          <h3>Upcoming Assignments</h3>
          <button class="btn sm ghost" data-act="nav" data-v="tasks">View All</button>
        </div>
        ${taskRowsHtml}
      </div>
    </div>

    ${S.quote ? `
      <div class="card" style="margin-top:18px;background:var(--bg-subtle);border-left:4px solid var(--brand)">
        <p style="font-style:italic;font-size:14px;color:var(--ink-secondary)">“${esc(S.quote.text)}”</p>
        <p class="mut sm" style="margin-top:5px;font-weight:600">— ${esc(S.quote.author)}</p>
      </div>
    ` : ''}
  `;
}

/* ==========================================================================
   VIEW: TIMETABLE (WITH WORKING DAY FILTERS & RESPONSIVE GRID)
   ========================================================================== */
function ttView() {
  const D = S.data;
  const todayDow = dow(new Date());

  const pills = [
    `<button class="seg-btn ${S.ttFilter === 'all' ? 'active' : ''}" data-act="tt-filter" data-f="all">All Days</button>`
  ].concat(DAYS.slice(0, 6).map((d, i) => `
    <button class="seg-btn ${S.ttFilter === i ? 'active' : ''} ${i === todayDow ? 'bold' : ''}" data-act="tt-filter" data-f="${i}">
      ${d} ${i === todayDow ? '•' : ''}
    </button>
  `)).join('');

  const daysToShow = S.ttFilter === 'all' ? [0, 1, 2, 3, 4, 5] : [+S.ttFilter];

  const weekColsHtml = daysToShow.map(i => {
    const dayClasses = D.timetable.filter(x => x.day === i).sort(byStart);
    return `
      <div class="day-column">
        <div class="day-head">
          <span class="day-title">${FULLDAYS[i]}</span>
          ${i === todayDow ? '<span class="badge primary sm">Today</span>' : ''}
        </div>
        ${dayClasses.map(it => {
          const s = subj(it.subject);
          return `
            <button class="class-card-tt" style="--c:${esc(s.color)}" data-act="tt-edit" data-id="${esc(it.id)}">
              <div class="tt-subj">${esc(s.name)}</div>
              <div class="tt-time">${fmtT(it.start)} – ${fmtT(it.end)}</div>
              ${it.room ? `<div class="tt-room">${icon('home', 12)} ${esc(it.room)}</div>` : ''}
            </button>
          `;
        }).join('') || '<p class="mut xs" style="text-align:center;padding:20px 0">No classes</p>'}
      </div>
    `;
  }).join('');

  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">Lecture Timetable</h1>
        <p class="page-sub">Tap any lecture to edit time, room, or remove it.</p>
      </div>
      <div class="actions-row">
        <button class="btn primary" data-act="tt-add">${icon('plus')} Add Lecture</button>
      </div>
    </div>

    <div class="segmented" style="margin-bottom:16px">
      ${pills}
    </div>

    <div class="week-grid" id="week-grid">
      ${weekColsHtml}
    </div>
  `;
}

/* ==========================================================================
   VIEW: ATTENDANCE
   ========================================================================== */
function attView() {
  const D = S.data, target = D.settings.target, ov = overall();
  const ovState = stateOf(ov, target);

  const cardsHtml = D.subjects.map(s => {
    const p = subjPct(s);
    const st = stateOf(p, target);
    const v = verdict(s);
    return `
      <div class="att-card">
        <div>
          <div class="att-header">
            <div class="att-subj-wrap">
              <span class="att-dot" style="--c:${esc(s.color)}"></span>
              <div>
                <h3 style="font-size:15.5px">${esc(s.name)}</h3>
                <span class="mut sm">${esc(s.code || 'Course')} · ${s.attended} of ${s.total} attended</span>
              </div>
            </div>
            <div class="att-big-pct ${st}">${Math.round(p)}%</div>
          </div>

          <div class="bar-track" style="margin:14px 0 10px">
            <div class="bar-fill" style="width:${Math.min(p, 100)}%;background:var(--${st})"></div>
            <div class="bar-target-tick" style="left:${target}%" title="Target ${target}%"></div>
          </div>

          <div class="bunk-verdict ${v.k}">
            ${esc(v.txt)}
          </div>
        </div>

        <div style="display:flex;align-items:center;gap:8px;border-top:1px solid var(--line);padding-top:12px;margin-top:4px">
          <button class="btn sm" data-act="att-extra" data-id="${esc(s.id)}" data-s="P">+ Present</button>
          <button class="btn sm" data-act="att-extra" data-id="${esc(s.id)}" data-s="A">+ Absent</button>
          <span class="grow"></span>
          <button class="icon-btn" data-act="sub-edit" data-id="${esc(s.id)}" aria-label="Edit course">${icon('edit', 15)}</button>
        </div>
      </div>
    `;
  }).join('') || `<p class="mut sm">No courses enrolled. Add your first subject to start tracking.</p>`;

  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">Attendance & Bunks</h1>
        <p class="page-sub">Target cutoff is <b>${target}%</b>. Predictions calculate safe skips automatically.</p>
      </div>
      <div class="actions-row">
        <button class="btn primary" data-act="sub-add">${icon('plus')} Add Subject</button>
      </div>
    </div>

    <div class="card" style="margin-bottom:18px;display:flex;align-items:center;justify-content:space-between;gap:16px;flex-wrap:wrap">
      <div>
        <h3>Semester Aggregate</h3>
        <p class="mut sm" style="margin-top:2px">Calculated across ${D.subjects.length} enrolled subjects.</p>
      </div>
      <div>
        <span class="badge ${ovState}" style="font-size:15px;padding:5px 13px">
          ${Math.round(ov)}% Overall
        </span>
      </div>
    </div>

    <div class="grid g2">
      ${cardsHtml}
    </div>
  `;
}

function mark(ttId, status) {
  const it = S.data.timetable.find(x => x.id === ttId);
  if (!it) return;
  const s = S.data.subjects.find(x => x.id === it.subject);
  if (!s) return;
  const key = ttId + '|' + iso(new Date());
  const cur = S.data.marks[key];

  if (cur) {
    s.total = Math.max(0, s.total - 1);
    if (cur === 'P') s.attended = Math.max(0, s.attended - 1);
    delete S.data.marks[key];
  }
  if (cur !== status) {
    s.total++;
    if (status === 'P') s.attended++;
    S.data.marks[key] = status;
    toast(`Marked ${status === 'P' ? 'Present' : 'Absent'} for ${s.name}`);
  } else {
    toast(`Cleared attendance status for ${s.name}`);
  }
  save();
  render();
}

function attExtra(id, status) {
  const s = S.data.subjects.find(x => x.id === id);
  if (!s) return;
  s.total++;
  if (status === 'P') s.attended++;
  save();
  render();
  toast(`${s.name}: Logged +1 ${status === 'P' ? 'Present' : 'Absent'}`);
}

/* ==========================================================================
   VIEW: TASKS / ASSIGNMENTS
   ========================================================================== */
function tasksView() {
  const D = S.data;
  let list = D.assignments.slice().sort((a,b) => new Date(a.due) - new Date(b.due));
  if (S.asFilter === 'pending') list = list.filter(a => !a.done);
  if (S.asFilter === 'done') list = list.filter(a => a.done).reverse();

  const countPending = D.assignments.filter(a => !a.done).length;
  const countOverdue = D.assignments.filter(a => !a.done && new Date(a.due) < Date.now()).length;

  const rows = list.map(a => {
    const isOver = !a.done && (new Date(a.due) < Date.now());
    const priBadge = a.priority === 'high' ? '<span class="badge bad sm">Urgent</span>' : a.priority === 'med' ? '<span class="badge warn sm">Medium</span>' : '';
    return `
      <div class="task-row ${a.done ? 'done' : ''}">
        <button class="task-check ${a.done ? 'checked' : ''}" data-act="as-toggle" data-id="${esc(a.id)}" aria-label="Toggle completed">
          ${icon('tick', 13)}
        </button>
        <div class="grow">
          <div class="task-title">${esc(a.title)}</div>
          ${a.details ? `<p class="mut sm" style="margin-top:2px">${esc(a.details)}</p>` : ''}
          <div class="task-meta">
            <span class="badge sm"><i class="badge-dot" style="color:${esc(subj(a.subject).color)}"></i> ${esc(subj(a.subject).name)}</span>
            <span class="${isOver ? 'badge sm bad' : 'mut'}">${isOver ? 'Overdue: ' + fmtDue(a.due) : fmtDue(a.due)}</span>
            ${priBadge}
          </div>
        </div>
        <button class="icon-btn" data-act="as-edit" data-id="${esc(a.id)}" aria-label="Edit task">${icon('edit', 15)}</button>
      </div>
    `;
  }).join('') || `<p class="mut sm" style="padding:20px 0;text-align:center">No tasks match this filter.</p>`;

  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">Assignments & Deadlines</h1>
        <p class="page-sub">${countPending} pending${countOverdue ? ` · <b style="color:var(--bad)">${countOverdue} overdue</b>` : ''}</p>
      </div>
      <div class="actions-row">
        <button class="btn primary" data-act="as-add">${icon('plus')} Add Task</button>
      </div>
    </div>

    <div class="segmented" style="margin-bottom:16px">
      ${[['pending','Pending'],['done','Completed'],['all','All Tasks']].map(([k,l]) => `
        <button class="seg-btn ${S.asFilter === k ? 'active' : ''}" data-act="as-filter" data-f="${k}">${l}</button>
      `).join('')}
    </div>

    <div class="card">
      ${rows}
    </div>
  `;
}

/* ==========================================================================
   VIEW: NOTES & AI COPILOT (FIXED GRANULAR SEARCH WITHOUT FOCUS LOSS)
   ========================================================================== */
const sortedNotes = () => S.data.notes.slice().sort((a,b) => (b.pinned - a.pinned) || (b.updated - a.updated));

function renderNoteItemsHtml() {
  const q = S.noteQ.trim().toLowerCase();
  const filtered = sortedNotes().filter(n => !q || (n.title + ' ' + n.body + ' ' + subj(n.subject).name).toLowerCase().includes(q));

  return filtered.map(n => `
    <button class="note-item ${n.id === S.noteId ? 'active' : ''}" data-act="note-open" data-id="${esc(n.id)}">
      <div class="note-item-title">
        ${n.pinned ? icon('pin', 13) : ''}
        <span class="truncate">${esc(n.title || 'Untitled Note')}</span>
        ${(n.images && n.images.length) ? `<span class="badge sm" style="margin-left:4px;font-size:10px">${n.images.length} 📷</span>` : ''}
      </div>
      <div class="note-item-preview">${esc(n.body.slice(0, 95) || 'Empty document')}</div>
    </button>
  `).join('') || '<p class="mut xs" style="text-align:center;padding:16px 0">No matching notes.</p>';
}

function notesView() {
  const D = S.data;
  if (!S.noteId && D.notes.length) {
    S.noteId = sortedNotes()[0].id;
  }
  const cur = D.notes.find(x => x.id === S.noteId);

  const editorHtml = cur ? `
    <div class="note-editor-card card">
      <div style="display:flex;align-items:center;justify-content:space-between;gap:12px">
        <select id="nsub" style="max-width:210px;padding:6px 10px;font-size:13px">
          <option value="">No Subject</option>
          ${D.subjects.map(s => `<option value="${esc(s.id)}" ${s.id === cur.subject ? 'selected' : ''}>${esc(s.name)}</option>`).join('')}
        </select>
        <div style="display:flex;gap:7px">
          <button class="icon-btn ${cur.pinned ? 'active' : ''}" data-act="note-pin" title="${cur.pinned ? 'Unpin' : 'Pin note'}">${icon('pin', 15)}</button>
          <button class="icon-btn danger" data-act="note-del" title="Delete note">${icon('trash', 15)}</button>
        </div>
      </div>

      <input id="ntitle" class="note-title-input" value="${esc(cur.title)}" placeholder="Note Title...">
      <textarea id="nbody" class="note-body-textarea" placeholder="Start typing your class notes...">${esc(cur.body)}</textarea>

      <div style="display:flex;gap:8px;flex-wrap:wrap;padding-top:10px;border-top:1px solid var(--line);align-items:center">
        <button class="btn sm" data-act="note-ai" data-k="sum">${icon('spark', 14)} Summarize</button>
        <button class="btn sm" data-act="note-ai" data-k="quiz">${icon('spark', 14)} Practice Quiz</button>
        <button class="btn sm" data-act="note-img-add" title="Attach image from camera or gallery">${icon('plus', 14)} Add Image</button>
        <input type="file" id="note-img-input" accept="image/*" multiple style="display:none">
        <span class="grow"></span>
        <span class="mut xs" id="notesavetag">Saved</span>
      </div>

      ${(cur.images && cur.images.length) ? `
        <div style="margin-top:12px">
          <div class="mut xs" style="margin-bottom:8px;font-weight:600">Attached images (${cur.images.length})</div>
          <div style="display:flex;flex-wrap:wrap;gap:10px" id="note-img-gallery">
            ${cur.images.map(img => `
              <div style="position:relative;width:110px;border:1px solid var(--line);border-radius:var(--radius-md);overflow:hidden;background:var(--bg-subtle)">
                <img src="${esc(img.dataUrl)}" alt="${esc(img.name || 'Note image')}" style="width:100%;height:80px;object-fit:cover;display:block;cursor:pointer" data-act="note-img-view" data-id="${esc(img.id)}" title="Click to view">
                <div style="padding:4px 6px;font-size:10px;color:var(--ink-muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis">${esc(img.name || 'Image')}</div>
                <button class="icon-btn" data-act="note-img-del" data-id="${esc(img.id)}" title="Remove image" style="position:absolute;top:4px;right:4px;width:24px;height:24px;background:rgba(0,0,0,0.55);border:none;color:#fff;border-radius:50%">
                  ${icon('x', 12)}
                </button>
              </div>
            `).join('')}
          </div>
        </div>
      ` : ''}

      <div id="noteai">${S.noteAI[cur.id] ? `<div class="card" style="background:var(--bg-subtle);margin-top:10px">${md(S.noteAI[cur.id].text || 'Analyzing...')}</div>` : ''}</div>
    </div>
  ` : `
    <div class="card" style="padding:60px 20px;text-align:center">
      <p class="mut sm">Select a note from the left or create a new one to begin.</p>
    </div>
  `;

  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">Lecture Notes & AI Summaries</h1>
        <p class="page-sub">Auto-saved Markdown notes with instant flashcard generation.</p>
      </div>
      <div class="actions-row">
        <button class="btn primary" data-act="note-new">${icon('plus')} New Note</button>
      </div>
    </div>

    <div class="notes-layout">
      <div class="notes-sidebar">
        <input id="noteq" placeholder="Filter notes..." value="${esc(S.noteQ)}" style="margin-bottom:6px">
        <div class="card note-list-card" id="noteslist">
          ${renderNoteItemsHtml()}
        </div>
      </div>
      <div class="grow" id="note-editor-wrap">
        ${editorHtml}
      </div>
    </div>
  `;
}

async function noteAI(kind) {
  const n = S.data.notes.find(x => x.id === S.noteId);
  if (!n) return;
  if (!n.body.trim()) { toast('Please write some content in the note first!'); return; }

  const id = n.id;
  S.noteAI[id] = { text: 'Analyzing your lecture notes...' };
  const aiBox = $('#noteai');
  if (aiBox) aiBox.innerHTML = `<div class="card" style="background:var(--bg-subtle);margin-top:10px"><p class="mut sm">Generating AI study guide...</p></div>`;

  const prompt = (kind === 'sum'
    ? 'Summarize these notes into 4 crisp bullet points followed by 3 key terminology definitions.'
    : 'Write 4 practice multiple choice / conceptual questions based on these notes followed by an Answers section.')
    + `\n\nSubject: ${subj(n.subject).name}\nTitle: ${n.title}\nContent:\n${n.body.slice(0, 3000)}`;

  const key = (S.data.settings.geminiKey || '').trim();
  try {
    if (key) {
      const resp = await API.gemini(prompt, key);
      S.noteAI[id] = { text: resp };
    } else {
      await new Promise(r => setTimeout(r, 400));
      S.noteAI[id] = {
        text: kind === 'sum'
          ? `### Summary for ${n.title}\n- **Core Concept**: Core lecture fundamentals detailed in notes.\n- **Preparation**: Review key formulas and implementation steps.\n- **Application**: Practice test problems on this topic.\n\n*(Add your Gemini key in Settings for full neural model summaries!)*`
          : `### Practice Questions for ${n.title}\n1. What is the fundamental mechanism behind ${n.title}?\n2. What are the time and space complexity bounds?\n3. When should this approach be favored over alternatives?\n\n**Answers**\nVerify with your notes above!`
      };
    }
  } catch (e) {
    S.noteAI[id] = { text: `Error: ${e.message}` };
  }
  if (aiBox) aiBox.innerHTML = `<div class="card" style="background:var(--bg-subtle);margin-top:10px">${md(S.noteAI[id].text)}</div>`;
}

/* ==========================================================================
   VIEW: CHAT / ASK AI (WITH TEXTAREA AUTOSIZE & MIC STATE)
   ========================================================================== */
function chatView() {
  const chips = [
    'What classes do I have today?',
    'Can I safely bunk my next class?',
    'What assignments are due this week?',
    'Give me a personalized study plan'
  ];
  const micActive = S.rec && S.rec.listening;

  const msgsHtml = S.chat.map(m => `
    <div class="msg-row ${m.role}">
      <div class="msg-avatar">${m.role === 'assistant' ? icon('spark', 15) : esc(S.user.name.charAt(0))}</div>
      <div class="msg-bubble">
        ${m.role === 'assistant' ? (m.text ? md(m.text) : '<span class="mut">Thinking...</span>') : esc(m.text)}
      </div>
    </div>
  `).join('') || `
    <div class="msg-row assistant">
      <div class="msg-avatar">${icon('spark', 15)}</div>
      <div class="msg-bubble">
        <p>Hello <b>${esc(S.user.name.split(' ')[0])}</b>! I am your Campus Desk AI Copilot. I have live access to your timetable, attendance records, deadlines, and notes. How can I help you today?</p>
      </div>
    </div>
  `;

  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">Ask AI Copilot</h1>
        <p class="page-sub">Direct access to your academic schedule, bunk calculators, and study notes.</p>
      </div>
      <div class="actions-row">
        <button class="btn sm ghost" data-act="chat-clear">Clear History</button>
      </div>
    </div>

    <div class="chat-window">
      <div id="chatlog" class="chat-messages">
        ${msgsHtml}
      </div>

      <div class="chat-prompts-bar">
        ${chips.map(c => `<button class="prompt-chip" data-act="chip" data-q="${esc(c)}">${esc(c)}</button>`).join('')}
      </div>

      <form id="chatform" class="chat-input-bar">
        <textarea id="chatin" class="chat-textarea grow" rows="1" placeholder="${S.busy ? 'AI is replying...' : 'Ask about classes, deadlines, attendance, or concepts...'}" aria-label="Message" ${S.busy ? 'disabled' : ''}></textarea>
        <button type="button" id="micbtn" class="icon-btn ${micActive ? 'listening' : ''}" data-act="voice" title="Speech to text" aria-pressed="${micActive ? 'true' : 'false'}">${icon('mic', 18)}</button>
        <button type="submit" id="chatsubmit" class="btn primary" aria-label="Send message" ${S.busy ? 'disabled' : ''}>${icon('send', 17)}</button>
      </form>
    </div>
  `;
}

function renderChat() {
  if (S.view !== 'chat') return;
  const l = $('#chatlog');
  if (l) {
    l.innerHTML = S.chat.map(m => `
      <div class="msg-row ${m.role}">
        <div class="msg-avatar">${m.role === 'assistant' ? icon('spark', 15) : esc(S.user.name.charAt(0))}</div>
        <div class="msg-bubble">
          ${m.role === 'assistant' ? (m.text ? md(m.text) : '<span class="mut">Thinking...</span>') : esc(m.text)}
        </div>
      </div>
    `).join('');
    l.scrollTop = l.scrollHeight;
  }
  const submitBtn = $('#chatsubmit');
  const chatInput = $('#chatin');
  if (submitBtn) submitBtn.disabled = S.busy;
  if (chatInput) {
    chatInput.disabled = S.busy;
    if (S.busy) {
      chatInput.placeholder = 'AI is replying...';
    } else {
      chatInput.placeholder = 'Ask about classes, deadlines, attendance, or concepts...';
      // Restore focus after AI finishes so user can keep typing
      if (document.activeElement !== chatInput) {
        setTimeout(() => chatInput.focus(), 30);
      }
    }
  }
}

/* ==========================================================================
   VIEW: TOOLS (POMODORO, FLASHCARDS, GPA, LOOKUP)
   ========================================================================== */
function toolsView() {
  const tabs = [
    ['study', 'Study Timer'],
    ['cards', 'Flashcards'],
    ['gpa', 'GPA Calculator'],
    ['lookup', 'Quick Lookup']
  ];
  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">Academic Tools & Utilities</h1>
        <p class="page-sub">Pomodoro study timer, interactive flashcards, GPA calculations, and dictionary.</p>
      </div>
    </div>

    <div class="segmented" style="margin-bottom:18px">
      ${tabs.map(([k,l]) => `
        <button class="seg-btn ${S.toolsTab === k ? 'active' : ''}" data-act="tools-tab" data-t="${k}">${l}</button>
      `).join('')}
    </div>

    <div id="tools-content">
      ${toolsContent()}
    </div>
  `;
}

function toolsContent() {
  if (S.toolsTab === 'study') {
    const p = S.pomo;
    const st = (S.data && S.data.settings) || {};
    const focusMin = Math.max(1, Math.min(180, +(st.focusMin || p.customFocus || 25)));
    const breakMin = Math.max(1, Math.min(60, +(st.breakMin || p.customBreak || 5)));
    // Keep S.pomo in sync
    p.customFocus = focusMin;
    p.customBreak = breakMin;

    const mm = Math.floor(p.left / 60), ss = p.left % 60;
    const fullFocus = focusMin * 60;
    const fullBreak = breakMin * 60;
    const isTotal = (p.mode === 'focus' && p.left === fullFocus) || (p.mode === 'break' && p.left === fullBreak);
    const btnLabel = p.run ? 'Pause' : isTotal ? (p.mode === 'focus' ? 'Start Focus' : 'Start Break') : 'Resume';

    return `
      <div class="card pomo-container">
        <span class="badge ${p.mode === 'focus' ? 'primary' : 'ok'}" style="font-size:13.5px;padding:5px 14px">
          ${p.mode === 'focus' ? `🎯 Focus Block (${focusMin} min)` : `☕ Break Session (${breakMin} min)`}
        </span>
        <div class="pomo-time-display" id="pomotime">${pad(mm)}:${pad(ss)}</div>
        <p class="mut sm" style="margin-bottom:14px">Completed Sessions: <b>${p.done}</b></p>

        <div style="display:flex;gap:10px;flex-wrap:wrap;justify-content:center;margin-bottom:18px">
          <button class="btn primary" id="pomobtn" data-act="pomo-toggle" style="padding:10px 24px">${btnLabel}</button>
          <button class="btn" data-act="pomo-skip">Next Block</button>
          <button class="btn ghost" data-act="pomo-reset">Reset</button>
        </div>

        <div style="width:100%;max-width:340px;margin:0 auto;padding-top:16px;border-top:1px solid var(--line)">
          <p class="mut sm" style="margin-bottom:10px;font-weight:600">Custom durations</p>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;text-align:left">
            <div class="form-field">
              <label for="pomo-focus" style="font-size:12px">Focus (minutes)</label>
              <input id="pomo-focus" type="number" min="1" max="180" value="${focusMin}"
                     ${p.run ? 'disabled' : ''} style="padding:8px 10px;font-size:14px">
            </div>
            <div class="form-field">
              <label for="pomo-break" style="font-size:12px">Break (minutes)</label>
              <input id="pomo-break" type="number" min="1" max="60" value="${breakMin}"
                     ${p.run ? 'disabled' : ''} style="padding:8px 10px;font-size:14px">
            </div>
          </div>
          <div style="display:flex;gap:8px;margin-top:12px;justify-content:center">
            <button class="btn sm primary" data-act="pomo-apply" ${p.run ? 'disabled' : ''}>Apply &amp; Reset Timer</button>
            <button class="btn sm ghost" data-act="pomo-presets" ${p.run ? 'disabled' : ''}>Presets</button>
          </div>
          <p class="mut xs" style="margin-top:8px;text-align:center">Changes apply on next start / reset. Timer is locked while running.</p>
        </div>
      </div>
    `;
  }

  if (S.toolsTab === 'cards') {
    if (!S.cards.length) buildCards();
    const cur = S.cards[S.cardI] || S.cards[0];
    return `
      <div class="card">
        <div class="card-head">
          <h3>Interactive Revision Deck</h3>
          <span class="mut sm">${S.cardI + 1} of ${S.cards.length}</span>
        </div>
        <div class="flashcard-stage" id="active-card" data-act="card-flip" tabindex="0" role="button" aria-label="Flashcard: ${esc(cur.q)}. Click or press Enter to flip.">
          <div class="flashcard-inner">
            <div class="flashcard-face flashcard-front">
              <span class="badge sm" style="position:absolute;top:14px;left:14px">${esc(cur.from)}</span>
              <p class="mut xs" style="text-transform:uppercase;letter-spacing:0.05em;margin-bottom:8px">Question (Tap to flip)</p>
              <h2 style="font-size:21px;line-height:1.4">${esc(cur.q)}</h2>
            </div>
            <div class="flashcard-face flashcard-back">
              <span class="badge sm" style="position:absolute;top:14px;left:14px">${esc(cur.from)}</span>
              <p class="mut xs" style="text-transform:uppercase;letter-spacing:0.05em;margin-bottom:8px">Answer</p>
              <h2 style="font-size:19px;line-height:1.4">${esc(cur.a)}</h2>
            </div>
          </div>
        </div>
        <div style="display:flex;align-items:center;justify-content:space-between;margin-top:16px">
          <button class="btn" data-act="card-prev">← Previous</button>
          <button class="btn" data-act="card-rebuild">${icon('spark', 15)} Rebuild from Notes</button>
          <button class="btn primary" data-act="card-next">Next →</button>
        </div>
      </div>
    `;
  }

  if (S.toolsTab === 'gpa') {
    const D = S.data;
    let totalCredits = 0, totalPts = 0;
    (D.grades || []).forEach(g => {
      const c = +g.credits || 0;
      totalCredits += c;
      totalPts += c * (GRADE_PT[g.grade] || 0);
    });
    const gpaVal = totalCredits ? (totalPts / totalCredits).toFixed(2) : '0.00';
    const gpaColorClass = totalCredits === 0 ? 'neutral' : (+gpaVal >= 7.5 ? 'ok' : +gpaVal >= 6.0 ? 'warn' : 'bad');

    const rows = (D.grades || []).map(g => `
      <div class="gpa-grid-row">
        <select data-act="g-sub" data-id="${esc(g.id)}">
          ${D.subjects.map(s => `<option value="${esc(s.id)}" ${s.id === g.subject ? 'selected' : ''}>${esc(s.name)}</option>`).join('')}
          <option value="" ${!g.subject ? 'selected' : ''}>Elective / Other</option>
        </select>
        <input type="number" min="1" max="10" value="${g.credits}" data-act="g-cr" data-id="${esc(g.id)}" aria-label="Credits">
        <select data-act="g-gr" data-id="${esc(g.id)}">
          ${Object.keys(GRADE_PT).map(k => `<option value="${k}" ${g.grade === k ? 'selected' : ''}>${k} (${GRADE_PT[k]} pts)</option>`).join('')}
        </select>
        <button class="icon-btn danger" data-act="g-del" data-id="${esc(g.id)}" aria-label="Remove course">${icon('x', 15)}</button>
      </div>
    `).join('') || '<p class="mut sm" style="padding:14px 0">No courses listed. Click below to add your courses.</p>';

    return `
      <div class="card">
        <div class="card-head">
          <div>
            <h3>Semester GPA Calculator</h3>
            <p class="mut sm">Credit-weighted average: Total Points / Total Credits</p>
          </div>
          <div style="text-align:right">
            <span class="att-big-pct ${gpaColorClass}">${gpaVal}</span>
            <div class="mut xs">${totalCredits} Total Credits</div>
          </div>
        </div>
        <div style="margin:14px 0">
          ${rows}
        </div>
        <button class="btn primary sm" data-act="g-add">${icon('plus')} Add Course</button>
      </div>
    `;
  }

  // Lookup Tool
  const L = S.lookup, W = S.wiki;
  return `
    <div class="card">
      <h3>Academic Reference & Concept Search</h3>
      <p class="mut sm" style="margin-top:2px">Search academic definitions via Dictionary API & Wikipedia REST.</p>
      <form id="lookform" style="display:flex;gap:10px;margin-top:14px">
        <input id="lookq" placeholder="Enter term e.g. polymorphism, operating system..." value="${esc(S.lookupQ)}">
        <button class="btn primary" type="submit">Search</button>
      </form>
      ${S.lookupBusy ? '<p class="mut sm" style="margin-top:14px">Querying APIs...</p>' : ''}
      ${L ? `
        <div class="card" style="margin-top:14px;background:var(--bg-subtle)">
          <div style="display:flex;align-items:center;gap:10px">
            <h3 style="font-size:17px">${esc(L.word)}</h3>
            <span class="badge sm primary">${esc(L.part)}</span>
            <span class="mut sm">${esc(L.phonetic)}</span>
          </div>
          <p style="margin-top:8px;font-size:14px">${esc(L.def)}</p>
          ${L.example ? `<p class="mut sm" style="margin-top:5px;font-style:italic">"${esc(L.example)}"</p>` : ''}
        </div>
      ` : ''}
      ${W ? `
        <div class="card" style="margin-top:14px;background:var(--bg-subtle)">
          <h3 style="font-size:17px">${esc(W.title)}</h3>
          <p style="margin-top:8px;font-size:14px;line-height:1.5">${esc(W.extract)}</p>
          ${W.url ? `<p style="margin-top:10px"><a href="${esc(W.url)}" target="_blank" rel="noopener">Read full article on Wikipedia ↗</a></p>` : ''}
        </div>
      ` : ''}
    </div>
  `;
}

/* ==========================================================================
   VIEW: NOTIFICATIONS
   ========================================================================== */
function alertsView() {
  const ns = notifs();
  const rows = ns.map(n => `
    <div class="task-row">
      <div style="width:34px;height:34px;border-radius:var(--radius-md);background:var(--${n.k}-subtle);color:var(--${n.k});display:grid;place-items:center;flex-shrink:0">
        ${icon(n.k === 'bad' ? 'bell' : 'clock', 17)}
      </div>
      <div class="grow">
        <div style="font-weight:600;font-size:14px;color:var(--ink)">${esc(n.title)}</div>
        <div class="mut sm" style="margin-top:2px">${esc(n.body)}</div>
      </div>
      <button class="btn sm" data-act="nav" data-v="${n.go}">View</button>
      <button class="icon-btn" data-act="n-dismiss" data-id="${esc(n.id)}" aria-label="Dismiss">${icon('x', 15)}</button>
    </div>
  `).join('') || `<p class="mut sm" style="padding:24px 0;text-align:center">All caught up! Zero unread notifications.</p>`;

  return `
    <div class="page-header">
      <div>
        <h1 class="page-title">Notification Center</h1>
        <p class="page-sub">Automated alerts for deadlines, attendance drops, and lecture start times.</p>
      </div>
      <div class="actions-row">
        ${ns.length ? `<button class="btn ghost sm" data-act="n-clear">Dismiss All</button>` : ''}
      </div>
    </div>
    <div class="card">
      ${rows}
    </div>
  `;
}

/* ==========================================================================
   MODALS SYSTEM (FIXED BACKDROP DRAG-SELECT DISMISS BUG)
   ========================================================================== */
let modalDelCallback = null;
let backdropMouseDown = false;

function openModal(title, body, onSave, del = null, submitLabel = 'Save Changes') {
  const d = $('#modal');
  if (d.open) d.close();
  modalDelCallback = del ? del.fn : null;

  d.innerHTML = `
    <form class="modal-form" autocomplete="off">
      <div class="modal-header">
        <h2>${title}</h2>
        <button type="button" class="icon-btn" data-act="m-cancel">${icon('x', 17)}</button>
      </div>
      ${body}
      <p id="modalerr" style="color:var(--bad);font-size:13px;font-weight:500;margin:0"></p>
      <div style="display:flex;align-items:center;gap:10px;margin-top:8px">
        ${del ? `<button type="button" class="btn danger" data-act="m-del" data-confirm="${esc(del.confirm || 'Tap again to delete')}">${esc(del.label || 'Delete')}</button>` : ''}
        <span class="grow"></span>
        <button type="button" class="btn ghost" data-act="m-cancel">Cancel</button>
        <button type="submit" class="btn primary">${submitLabel}</button>
      </div>
    </form>
  `;

  const f = d.querySelector('form');
  f.addEventListener('submit', async e => {
    e.preventDefault();
    const err = await onSave(Object.fromEntries(new FormData(f)));
    if (err) {
      $('#modalerr').textContent = err;
    } else {
      d.close();
    }
  });

  d.showModal();
}

function subjectModal(id) {
  const D = S.data;
  const s = id ? D.subjects.find(x => x.id === id) : null;
  const v = s || {
    name: '', code: '', attended: 0, total: 0, credits: 4,
    color: COLORS.find(c => !D.subjects.some(x => x.color === c)) || COLORS[0]
  };

  openModal(
    s ? 'Edit Subject' : 'Add Subject',
    `
      <div class="form-field">
        <label for="sn">Subject Name</label>
        <input id="sn" name="name" value="${esc(v.name)}" placeholder="e.g. Operating Systems" required>
      </div>
      <div class="form-field">
        <label for="sc">Course Code (Optional)</label>
        <input id="sc" name="code" value="${esc(v.code)}" placeholder="e.g. CS206">
      </div>
      <div class="form-row2">
        <div class="form-field">
          <label for="sa">Attended Classes</label>
          <input id="sa" name="attended" type="number" min="0" value="${v.attended}" required>
        </div>
        <div class="form-field">
          <label for="st">Total Classes Held</label>
          <input id="st" name="total" type="number" min="0" value="${v.total}" required>
        </div>
      </div>
      <div class="form-field">
        <label for="scr">Course Credits (Synced with GPA)</label>
        <input id="scr" name="credits" type="number" min="1" max="10" value="${v.credits || 3}">
      </div>
      <div class="form-field">
        <span class="field-lbl">Card Accent Color</span>
        <div class="color-picker-row">
          ${COLORS.map(c => `
            <label class="color-swatch-label">
              <input type="radio" name="color" value="${c}" ${c === v.color ? 'checked' : ''}>
              <span class="color-circle" style="--c:${c}"></span>
            </label>
          `).join('')}
        </div>
      </div>
    `,
    fd => {
      const name = (fd.name || '').trim();
      const a = parseInt(fd.attended, 10);
      const t = parseInt(fd.total, 10);
      if (!name) return 'Subject name is required.';
      if (isNaN(a) || isNaN(t) || a < 0 || t < 0) return 'Class counts must be non-negative integers.';
      if (a > t) return 'Attended classes cannot exceed total classes held.';

      const credits = Math.max(1, parseInt(fd.credits, 10) || 3);
      const rec = {
        name,
        code: (fd.code || '').trim(),
        attended: a,
        total: t,
        credits,
        color: fd.color || v.color
      };

      if (s) {
        Object.assign(s, rec);
        // Sync credit updates with existing GPA rows
        (D.grades || []).forEach(g => {
          if (g.subject === s.id) g.credits = credits;
        });
      } else {
        const newId = uid();
        D.subjects.push(Object.assign({ id: newId }, rec));
        // Add course entry to GPA automatically
        D.grades.push({ id: uid(), subject: newId, credits, grade: 'A' });
      }

      save();
      render();
      toast(s ? 'Subject updated.' : 'Subject added.');
    },
    s ? {
      label: 'Delete Subject',
      confirm: 'Delete subject, lectures, and GPA entries?',
      fn: () => {
        D.timetable = D.timetable.filter(x => x.subject !== s.id);
        D.assignments.forEach(a => { if (a.subject === s.id) a.subject = ''; });
        D.notes.forEach(n => { if (n.subject === s.id) n.subject = ''; });
        // Clean orphan rows from GPA list
        D.grades = D.grades.filter(g => g.subject !== s.id);
        D.subjects = D.subjects.filter(x => x.id !== s.id);
        save();
        render();
        toast('Subject deleted.');
      }
    } : null,
    s ? 'Save Changes' : 'Add Subject'
  );
}

function classModal(id) {
  const D = S.data;
  if (!D.subjects.length) {
    toast('Please add at least one subject first!');
    subjectModal();
    return;
  }
  const it = id ? D.timetable.find(x => x.id === id) : null;
  const v = it || { subject: D.subjects[0].id, day: S.ttDay, start: '09:00', end: '10:00', room: '' };

  openModal(
    it ? 'Edit Lecture' : 'Add Lecture',
    `
      <div class="form-field">
        <label for="cls_sub">Subject</label>
        <select id="cls_sub" name="subject">
          ${D.subjects.map(s => `<option value="${esc(s.id)}" ${s.id === v.subject ? 'selected' : ''}>${esc(s.name)}</option>`).join('')}
        </select>
      </div>
      <div class="form-field">
        <label for="cls_day">Day of Week</label>
        <select id="cls_day" name="day">
          ${DAYS.slice(0, 6).map((d, i) => `<option value="${i}" ${i === v.day ? 'selected' : ''}>${FULLDAYS[i]}</option>`).join('')}
        </select>
      </div>
      <div class="form-row2">
        <div class="form-field">
          <label for="cls_start">Starts At</label>
          <input id="cls_start" name="start" type="time" value="${v.start}" required>
        </div>
        <div class="form-field">
          <label for="cls_end">Ends At</label>
          <input id="cls_end" name="end" type="time" value="${v.end}" required>
        </div>
      </div>
      <div class="form-field">
        <label for="cls_room">Room / Lab (Optional)</label>
        <input id="cls_room" name="room" value="${esc(v.room)}" placeholder="e.g. Hall A-101">
      </div>
    `,
    fd => {
      const day = parseInt(fd.day, 10);
      if (!fd.start || !fd.end) return 'Please choose start and end times.';
      if (toMin(fd.end) <= toMin(fd.start)) return 'End time must be after start time.';

      const clash = D.timetable.find(x =>
        x.day === day &&
        x.id !== (it && it.id) &&
        toMin(x.start) < toMin(fd.end) &&
        toMin(x.end) > toMin(fd.start)
      );
      if (clash) {
        return `Overlaps with ${subj(clash.subject).name} (${fmtT(clash.start)} - ${fmtT(clash.end)}).`;
      }

      const rec = {
        subject: fd.subject,
        day,
        start: fd.start,
        end: fd.end,
        room: (fd.room || '').trim()
      };

      if (it) Object.assign(it, rec);
      else D.timetable.push(Object.assign({ id: uid() }, rec));

      S.ttDay = day;
      save();
      render();
      toast(it ? 'Lecture updated.' : 'Lecture added.');
    },
    it ? {
      label: 'Delete Lecture',
      fn: () => {
        D.timetable = D.timetable.filter(x => x.id !== it.id);
        save();
        render();
        toast('Lecture deleted.');
      }
    } : null,
    it ? 'Save Changes' : 'Add Lecture'
  );
}

function asModal(id) {
  const D = S.data;
  const a = id ? D.assignments.find(x => x.id === id) : null;
  const tmr = new Date(); tmr.setDate(tmr.getDate() + 1);
  const v = a || { title: '', subject: D.subjects[0] ? D.subjects[0].id : '', due: `${iso(tmr)}T23:59`, priority: 'med', details: '' };

  openModal(
    a ? 'Edit Assignment' : 'Add Assignment',
    `
      <div class="form-field">
        <label for="atitle">Assignment Title</label>
        <input id="atitle" name="title" value="${esc(v.title)}" placeholder="e.g. Lab Report 3" required>
      </div>
      <div class="form-field">
        <label for="asub">Subject</label>
        <select id="asub" name="subject">
          <option value="">General (No Subject)</option>
          ${D.subjects.map(s => `<option value="${esc(s.id)}" ${s.id === v.subject ? 'selected' : ''}>${esc(s.name)}</option>`).join('')}
        </select>
      </div>
      <div class="form-row2">
        <div class="form-field">
          <label for="adue">Submission Deadline</label>
          <input id="adue" name="due" type="datetime-local" value="${v.due}" required>
        </div>
        <div class="form-field">
          <label for="apri">Priority</label>
          <select id="apri" name="priority">
            <option value="high" ${v.priority === 'high' ? 'selected' : ''}>High</option>
            <option value="med" ${v.priority === 'med' ? 'selected' : ''}>Medium</option>
            <option value="low" ${v.priority === 'low' ? 'selected' : ''}>Low</option>
          </select>
        </div>
      </div>
      <div class="form-field">
        <label for="adet">Instructions / Notes (Optional)</label>
        <textarea id="adet" name="details" rows="3" placeholder="Submission criteria, questions to solve...">${esc(v.details)}</textarea>
      </div>
    `,
    fd => {
      const title = (fd.title || '').trim();
      if (!title) return 'Please specify an assignment title.';
      if (!fd.due || isNaN(new Date(fd.due))) return 'Please provide a valid deadline date.';

      const rec = {
        title,
        subject: fd.subject || '',
        due: fd.due,
        priority: fd.priority,
        details: (fd.details || '').trim()
      };

      if (a) Object.assign(a, rec);
      else D.assignments.push(Object.assign({ id: uid(), done: false }, rec));

      save();
      render();
      toast(a ? 'Assignment updated.' : 'Assignment added.');
    },
    a ? {
      label: 'Delete Assignment',
      fn: () => {
        D.assignments = D.assignments.filter(x => x.id !== a.id);
        save();
        render();
        toast('Assignment deleted.');
      }
    } : null,
    a ? 'Save Changes' : 'Add Assignment'
  );
}

function profileModal() {
  const D = S.data, st = D.settings;
  openModal(
    'Settings & Preferences',
    `
      <div class="form-field">
        <label for="st_target">Attendance Cutoff Target (%)</label>
        <input id="st_target" name="target" type="number" min="50" max="95" value="${st.target}" required>
        <span class="mut xs">Used for automatic safe bunk prediction calculations.</span>
      </div>
      <div class="form-field">
        <label for="st_due">Deadline Advance Alert Window</label>
        <select id="st_due" name="dueHours">
          <option value="24" ${st.dueHours === 24 ? 'selected' : ''}>24 Hours</option>
          <option value="48" ${st.dueHours === 48 ? 'selected' : ''}>48 Hours (2 Days)</option>
          <option value="72" ${st.dueHours === 72 ? 'selected' : ''}>72 Hours (3 Days)</option>
          <option value="168" ${st.dueHours === 168 ? 'selected' : ''}>1 Week</option>
        </select>
      </div>
      <div class="form-field">
        <label for="st_city">Campus City (For Weather API)</label>
        <input id="st_city" name="city" value="${esc(st.city || 'Pune')}">
      </div>
      <div class="form-field">
        <label for="st_theme">Appearance Theme</label>
        <select id="st_theme" name="theme">
          <option value="system" ${st.theme === 'system' ? 'selected' : ''}>Match Operating System</option>
          <option value="light" ${st.theme === 'light' ? 'selected' : ''}>Light Theme</option>
          <option value="dark" ${st.theme === 'dark' ? 'selected' : ''}>Dark Theme</option>
        </select>
      </div>
      <div class="form-field">
        <label for="st_key">Google Gemini API Key (Optional)</label>
        <div style="display:flex;gap:8px;align-items:center">
          <input id="st_key" name="geminiKey" type="password" value="${esc(st.geminiKey || '')}" placeholder="AIzaSy..." style="flex:1">
          ${st.geminiKey ? '<button type="button" class="btn sm danger" data-act="clear-key" title="Remove key">Clear</button>' : ''}
        </div>
        <span class="mut xs">${st.geminiKey ? '✓ Key is set (stored locally only). ' : ''}Stripped from backup exports. Free key at <a href="https://aistudio.google.com/apikey" target="_blank" rel="noopener">Google AI Studio</a>.</span>
      </div>
      <div class="form-field" style="margin-top:4px">
        <label style="display:flex;align-items:center;gap:8px;cursor:pointer">
          <input type="checkbox" name="notify" style="width:auto" ${st.notify ? 'checked' : ''}>
          <span>Enable Browser Notifications for class start times & deadlines</span>
        </label>
      </div>
      <div class="form-field" style="margin-top:4px">
        <span class="field-lbl">Password Recovery</span>
        <div><button type="button" class="btn sm" data-act="sec-q">Set / Change Security Question</button></div>
        <span class="mut xs">Lets you reset your password if you forget it. Opening this closes Settings, so save any changes first.</span>
      </div>
      <div style="display:flex;gap:10px;margin-top:6px">
        <button type="button" class="btn sm" data-act="export">Download Backup (JSON)</button>
        <button type="button" class="btn sm" data-act="import">Restore Backup (JSON)</button>
      </div>
    `,
    fd => {
      const t = parseInt(fd.target, 10);
      if (isNaN(t) || t < 50 || t > 95) return 'Target percentage must be between 50% and 95%.';

      st.target = t;
      st.dueHours = parseInt(fd.dueHours, 10);
      st.city = (fd.city || 'Pune').trim();
      st.theme = fd.theme || 'system';
      st.geminiKey = (fd.geminiKey || '').trim();
      st.notify = !!fd.notify;

      if (st.notify && 'Notification' in window && Notification.permission !== 'granted') {
        Notification.requestPermission();
      }

      store.set('cd:theme', st.theme);
      save();
      applyTheme();
      render();
      refreshCampus();
      toast('Preferences updated.');
    },
    {
      label: 'Delete Account Data',
      confirm: 'Erase all student records permanently?',
      fn: () => {
        const id = S.user.id;
        store.set('cd:users', getUsers().filter(u => u.id !== id));
        store.set('cd:data:' + id, null);
        store.set('cd:chat:' + id, null);
        logout();
        toast('Account data cleared.');
      }
    },
    'Save Changes'
  );
}

/* ==========================================================================
   COMMAND SEARCH PALETTE
   ========================================================================== */
function cmdItems(q) {
  if (!S.data) return [];
  q = (q || '').toLowerCase().trim();
  const items = [
    { cmd: 'nav', arg: 'home', label: 'Go to Dashboard', hint: 'Overview' },
    { cmd: 'nav', arg: 'tt', label: 'Go to Timetable', hint: 'Schedule' },
    { cmd: 'nav', arg: 'att', label: 'Go to Attendance', hint: 'Safe Bunks' },
    { cmd: 'nav', arg: 'tasks', label: 'Go to Assignments', hint: 'Submissions' },
    { cmd: 'nav', arg: 'notes', label: 'Go to Lecture Notes', hint: 'Study Docs' },
    { cmd: 'nav', arg: 'chat', label: 'Ask AI Copilot', hint: 'Assistant' },
    { cmd: 'nav', arg: 'tools', label: 'Open Study Tools', hint: 'Timer / GPA' },
    { cmd: 'as-add', arg: '', label: 'Create New Assignment', hint: 'Action' },
    { cmd: 'tt-add', arg: '', label: 'Schedule New Lecture', hint: 'Action' },
    { cmd: 'note-new', arg: '', label: 'Create New Lecture Note', hint: 'Action' },
    { cmd: 'profile', arg: '', label: 'Settings & Gemini Key', hint: 'Preferences' }
  ];

  S.data.assignments.filter(a => !a.done).forEach(a => {
    items.push({ cmd: 'as-edit', arg: a.id, label: a.title, hint: 'Assignment' });
  });
  S.data.notes.forEach(n => {
    items.push({ cmd: 'note-open', arg: n.id, label: n.title || 'Untitled Note', hint: 'Note' });
  });
  S.data.subjects.forEach(s => {
    items.push({ cmd: 'sub-edit', arg: s.id, label: s.name, hint: 'Subject' });
  });

  return items.filter(x => !q || (x.label + ' ' + x.hint).toLowerCase().includes(q)).slice(0, 10);
}

function openCmd() {
  const d = $('#cmd');
  S.cmdI = 0;
  d.innerHTML = `
    <div class="cmd-input-wrap">
      ${icon('search', 18)}
      <input id="cmdq" class="cmd-input grow" placeholder="Type a command or search courses, notes, tasks..." autocomplete="off">
    </div>
    <div id="cmdlist" class="cmd-results"></div>
  `;
  if (!d.open) d.showModal();
  paintCmd();
  const inp = $('#cmdq');
  if (inp) inp.focus();
}

function paintCmd() {
  const q = ($('#cmdq') && $('#cmdq').value) || '';
  const items = cmdItems(q);
  const box = $('#cmdlist');
  if (!box) return;
  if (!items.length) {
    box.innerHTML = '<p class="mut xs" style="padding:14px;text-align:center">No matching commands.</p>';
    return;
  }
  S.cmdI = Math.max(0, Math.min(S.cmdI, items.length - 1));
  box.innerHTML = items.map((it, idx) => `
    <button class="cmd-item ${idx === S.cmdI ? 'selected' : ''}" data-act="cmd-go" data-cmd="${it.cmd}" data-arg="${esc(it.arg)}">
      <span>${esc(it.label)}</span>
      <span class="mut xs">${esc(it.hint)}</span>
    </button>
  `).join('');
}

function runCmd(cmd, arg) {
  const d = $('#cmd');
  if (d.open) d.close();
  if (cmd === 'nav') { S.view = arg; render(); }
  else if (cmd === 'as-add') asModal();
  else if (cmd === 'as-edit') asModal(arg);
  else if (cmd === 'tt-add') classModal();
  else if (cmd === 'sub-edit') subjectModal(arg);
  else if (cmd === 'note-new') {
    const n = { id: uid(), title: '', body: '', subject: '', pinned: false, updated: Date.now(), images: [] };
    S.data.notes.unshift(n);
    S.noteId = n.id;
    S.view = 'notes';
    save();
    render();
  }
  else if (cmd === 'note-open') { S.view = 'notes'; S.noteId = arg; render(); }
  else if (cmd === 'profile') profileModal();
}

/* ==========================================================================
   DRIFT-FREE POMODORO TIMER & SINGLE AUDIOCONTEXT
   ========================================================================== */
let audioCtx = null;
function playChime() {
  try {
    if (!audioCtx || audioCtx.state === 'closed') {
      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    }
    if (audioCtx.state === 'suspended') {
      audioCtx.resume();
    }
    const osc = audioCtx.createOscillator();
    const gain = audioCtx.createGain();
    osc.connect(gain);
    gain.connect(audioCtx.destination);
    const t = audioCtx.currentTime;
    osc.frequency.setValueAtTime(587.33, t); // D5
    osc.frequency.exponentialRampToValueAtTime(880, t + 0.25); // A5
    gain.gain.setValueAtTime(0.2, t);
    gain.gain.exponentialRampToValueAtTime(0.001, t + 0.6);
    osc.start(t);
    osc.stop(t + 0.6);
  } catch (e) {}
}

function pomoToggle() {
  const p = S.pomo;
  if (p.run) {
    // Pausing: compute remaining time from timestamp and clear target
    if (p.targetEndTime) {
      p.left = Math.max(0, Math.round((p.targetEndTime - Date.now()) / 1000));
    }
    p.targetEndTime = null;
    p.run = false;
  } else {
    // Resuming/Starting: set accurate future target timestamp
    p.targetEndTime = Date.now() + (p.left * 1000);
    p.run = true;
  }
  updatePomoUI();
}

function pomoFinish() {
  const p = S.pomo;
  const focusSec = Math.max(60, (p.customFocus || 25) * 60);
  const breakSec = Math.max(60, (p.customBreak || 5) * 60);
  p.run = false;
  p.targetEndTime = null;
  playChime();
  if (p.mode === 'focus') {
    p.done++;
    p.mode = 'break';
    p.left = breakSec;
    toast(`🎉 Focus session completed! Take a ${p.customBreak || 5}-minute break.`);
    sendBrowserNotification('Focus Block Done', `Great job! Take a ${p.customBreak || 5}-minute break to stretch.`);
  } else {
    p.mode = 'focus';
    p.left = focusSec;
    toast('Break over. Ready for your next focus session!');
    sendBrowserNotification('Break Completed', `Time to start your next ${p.customFocus || 25}-minute focus session.`);
  }
  if (S.view === 'tools' && S.toolsTab === 'study') {
    const el = $('#tools-content');
    if (el) el.innerHTML = toolsContent();
  }
}

function updatePomoUI() {
  const el = $('#pomotime');
  if (el) {
    const mm = Math.floor(S.pomo.left / 60), ss = S.pomo.left % 60;
    el.textContent = pad(mm) + ':' + pad(ss);
  }
  const btn = $('#pomobtn');
  if (btn) {
    const p = S.pomo;
    const isTotal = (p.mode === 'focus' && p.left === 25 * 60) || (p.mode === 'break' && p.left === 5 * 60);
    btn.textContent = p.run ? 'Pause' : isTotal ? (p.mode === 'focus' ? 'Start Focus' : 'Start Break') : 'Resume';
  }
}

function tick() {
  // Drift-free Pomodoro calculation
  if (S.pomo.run && S.pomo.targetEndTime) {
    S.pomo.left = Math.max(0, Math.round((S.pomo.targetEndTime - Date.now()) / 1000));
    if (S.pomo.left <= 0) {
      pomoFinish();
    } else {
      updatePomoUI();
    }
  }

  // Live clocks
  const clock = $('#liveclock');
  if (clock) {
    clock.textContent = new Date().toLocaleTimeString([], { hour:'numeric', minute:'2-digit', second:'2-digit' });
  }
  const eta = $('#liveeta');
  if (eta) {
    eta.textContent = nextClassEta();
  }

  // Periodic check (every 30 seconds) for hero card & notification changes
  const now = new Date();
  if (now.getSeconds() === 0 || now.getSeconds() === 30) {
    const tag = $('#hero-tag-lbl');
    const nx = nextClass();
    if (tag && nx) tag.textContent = nx.label;
  }
}

function sendBrowserNotification(title, body) {
  if (S.data && S.data.settings && S.data.settings.notify && 'Notification' in window && Notification.permission === 'granted') {
    try { new Notification(title, { body }); } catch (e) {}
  }
}

/* ==========================================================================
   TOAST & EXPORT / IMPORT (SAFE RESTORE & STRIPPED KEYS)
   ========================================================================== */
let toastTimeout = null;
function toast(msg) {
  const t = $('#toast');
  if (!t) return;
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(toastTimeout);
  toastTimeout = setTimeout(() => t.classList.remove('show'), 2400);
}

function exportData() {
  const safeData = JSON.parse(JSON.stringify(S.data));
  // Strip Gemini API key in plain text export for security
  if (safeData.settings) safeData.settings.geminiKey = '';

  const backup = {
    version: '2.1',
    exportedAt: new Date().toISOString(),
    user: { name: S.user.name, email: S.user.email },
    data: safeData,
    chat: S.chat
  };
  const blob = new Blob([JSON.stringify(backup, null, 2)], { type: 'application/json' });
  const a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = `campus-desk-backup-${iso(new Date())}.json`;
  a.click();
  URL.revokeObjectURL(a.href);
  toast('Backup file downloaded (API key omitted).');
}

function pickImport() {
  const inp = document.createElement('input');
  inp.type = 'file';
  inp.accept = 'application/json';
  inp.onchange = () => {
    const file = inp.files && inp.files[0];
    if (!file) return;
    const r = new FileReader();
    r.onload = () => {
      try {
        const parsed = JSON.parse(r.result);
        if (!parsed.data || typeof parsed.data !== 'object') throw new Error('Invalid format');
        
        if (!confirm('Restoring this backup will replace current courses, notes, and timetable. Continue?')) {
          return;
        }

        const base = emptyData();
        const mergedData = Object.assign(base, parsed.data);
        mergedData.settings = Object.assign(defaultSettings(), (parsed.data && parsed.data.settings) || {});
        // Preserve current user's local Gemini key if export didn't include one
        if (!mergedData.settings.geminiKey && S.data.settings.geminiKey) {
          mergedData.settings.geminiKey = S.data.settings.geminiKey;
        }

        S.data = mergedData;
        if (Array.isArray(parsed.chat)) S.chat = parsed.chat;
        save();
        buildCards();
        const m = $('#modal');
        if (m && m.open) m.close();
        render();
        toast('Backup successfully restored!');
      } catch (err) {
        toast('Invalid backup file. Restoration cancelled.');
      }
    };
    r.readAsText(file);
  };
  inp.click();
}

/* ==========================================================================
   VOICE SPEECH-TO-TEXT WITH VISUAL INDICATOR
   ========================================================================== */
function toggleVoice() {
  const SR = window.SpeechRecognition || window.webkitSpeechRecognition;
  if (!SR) {
    toast('Speech recognition is not supported in this browser.');
    return;
  }
  const micBtn = $('#micbtn');

  if (S.rec && S.rec.listening) {
    S.rec.stop();
    S.rec.listening = false;
    if (micBtn) {
      micBtn.classList.remove('listening');
      micBtn.setAttribute('aria-pressed', 'false');
    }
    return;
  }

  const rec = new SR();
  rec.lang = 'en-US';
  rec.interimResults = false;

  rec.onresult = ev => {
    const t = ev.results[0][0].transcript;
    const i = $('#chatin');
    if (i) {
      i.value = (i.value ? i.value + ' ' : '') + t;
      i.style.height = 'auto';
      i.style.height = Math.min(i.scrollHeight, 140) + 'px';
      i.focus();
    }
  };
  rec.onerror = e => {
    if (S.rec) S.rec.listening = false;
    if (micBtn) {
      micBtn.classList.remove('listening');
      micBtn.setAttribute('aria-pressed', 'false');
    }
    toast('Microphone error: ' + (e.error || 'Check permissions'));
  };
  rec.onend = () => {
    if (S.rec) S.rec.listening = false;
    if (micBtn) {
      micBtn.classList.remove('listening');
      micBtn.setAttribute('aria-pressed', 'false');
    }
  };

  try {
    rec.start();
    S.rec = rec;
    S.rec.listening = true;
    if (micBtn) {
      micBtn.classList.add('listening');
      micBtn.setAttribute('aria-pressed', 'true');
    }
    toast('Listening... Speak clearly.');
  } catch (err) {
    toast('Could not start microphone.');
  }
}

/* ==========================================================================
   EVENT DELEGATION (GRANULAR UPDATES)
   ========================================================================== */
document.addEventListener('click', e => {
  const el = e.target.closest('[data-act]');
  if (!el) return;

  if (el.hasAttribute('data-confirm') && !el.dataset.armed) {
    el.dataset.armed = '1';
    const old = el.innerHTML;
    el.textContent = el.dataset.confirm || 'Tap again to confirm';
    setTimeout(() => {
      if (el.isConnected) {
        delete el.dataset.armed;
        el.innerHTML = old;
      }
    }, 3000);
    return;
  }

  const act = el.dataset.act;
  const id = el.dataset.id;
  const D = S.data;

  switch (act) {
    case 'nav':
      S.view = el.dataset.v;
      const sheet = $('#more-sheet');
      if (sheet) sheet.classList.remove('open');
      render();
      window.scrollTo(0, 0);
      break;
    case 'more-open': {
      const s = $('#more-sheet');
      if (s) s.classList.add('open');
      break;
    }
    case 'more-close': {
      const s = $('#more-sheet');
      if (s) s.classList.remove('open');
      break;
    }
    case 'logout': logout(); break;
    case 'auth-tab': S.authTab = el.dataset.t; S.reset = null; render(); break;
    case 'auth-forgot': S.authTab = 'reset'; S.reset = { step: 1 }; render(); break;
    case 'auth-back': S.authTab = 'in'; S.reset = null; render(); break;
    case 'sec-q': secQuestionModal(); break;
    case 'demo': demo(); break;
    case 'theme-toggle': toggleTheme(); break;
    case 'profile': profileModal(); break;
    case 'load-sample':
      Object.assign(S.data, seed(), { settings: S.data.settings });
      save();
      buildCards();
      render();
      toast('Demo courses loaded!');
      break;
    case 'tt-filter':
      S.ttFilter = el.dataset.f;
      const wg = $('#week-grid');
      if (wg) {
        const daysToShow = S.ttFilter === 'all' ? [0, 1, 2, 3, 4, 5] : [+S.ttFilter];
        const todayDow = dow(new Date());
        wg.innerHTML = daysToShow.map(i => {
          const dayClasses = D.timetable.filter(x => x.day === i).sort(byStart);
          return `
            <div class="day-column">
              <div class="day-head">
                <span class="day-title">${FULLDAYS[i]}</span>
                ${i === todayDow ? '<span class="badge primary sm">Today</span>' : ''}
              </div>
              ${dayClasses.map(it => {
                const s = subj(it.subject);
                return `
                  <button class="class-card-tt" style="--c:${esc(s.color)}" data-act="tt-edit" data-id="${esc(it.id)}">
                    <div class="tt-subj">${esc(s.name)}</div>
                    <div class="tt-time">${fmtT(it.start)} – ${fmtT(it.end)}</div>
                    ${it.room ? `<div class="tt-room">${icon('home', 12)} ${esc(it.room)}</div>` : ''}
                  </button>
                `;
              }).join('') || '<p class="mut xs" style="text-align:center;padding:20px 0">No classes</p>'}
            </div>
          `;
        }).join('');
        // Update active class on filter buttons
        $$('.seg-btn[data-act="tt-filter"]').forEach(b => b.classList.toggle('active', b.dataset.f === S.ttFilter));
      } else {
        render();
      }
      break;
    case 'tt-add': classModal(); break;
    case 'tt-edit': classModal(id); break;
    case 'sub-add': subjectModal(); break;
    case 'sub-edit': subjectModal(id); break;
    case 'mark': mark(id, el.dataset.s); break;
    case 'mark-hero': mark(id, 'P'); break;
    case 'att-extra': attExtra(id, el.dataset.s); break;
    case 'as-add': asModal(); break;
    case 'as-edit': asModal(id); break;
    case 'as-filter': S.asFilter = el.dataset.f; render(); break;
    case 'as-toggle': {
      const task = D.assignments.find(x => x.id === id);
      if (task) {
        task.done = !task.done;
        save();
        render();
        if (task.done) confetti();
      }
      break;
    }
    case 'note-new': {
      const n = { id: uid(), title: '', body: '', subject: '', pinned: false, updated: Date.now(), images: [] };
      D.notes.unshift(n);
      S.noteId = n.id;
      S.noteQ = '';
      save();
      render();
      const inp = $('#ntitle');
      if (inp) inp.focus();
      break;
    }
    case 'note-open':
      S.noteId = id;
      // Granular editor update without full app destruction
      const editorWrap = $('#note-editor-wrap');
      if (editorWrap) {
        const curNote = D.notes.find(x => x.id === id);
        if (curNote) {
          editorWrap.innerHTML = `
            <div class="note-editor-card card">
              <div style="display:flex;align-items:center;justify-content:space-between;gap:12px">
                <select id="nsub" style="max-width:210px;padding:6px 10px;font-size:13px">
                  <option value="">No Subject</option>
                  ${D.subjects.map(s => `<option value="${esc(s.id)}" ${s.id === curNote.subject ? 'selected' : ''}>${esc(s.name)}</option>`).join('')}
                </select>
                <div style="display:flex;gap:7px">
                  <button class="icon-btn ${curNote.pinned ? 'active' : ''}" data-act="note-pin" title="${curNote.pinned ? 'Unpin' : 'Pin note'}">${icon('pin', 15)}</button>
                  <button class="icon-btn danger" data-act="note-del" title="Delete note">${icon('trash', 15)}</button>
                </div>
              </div>
              <input id="ntitle" class="note-title-input" value="${esc(curNote.title)}" placeholder="Note Title...">
              <textarea id="nbody" class="note-body-textarea" placeholder="Start typing your class notes...">${esc(curNote.body)}</textarea>
              <div style="display:flex;gap:8px;flex-wrap:wrap;padding-top:10px;border-top:1px solid var(--line);align-items:center">
                <button class="btn sm" data-act="note-ai" data-k="sum">${icon('spark', 14)} Summarize</button>
                <button class="btn sm" data-act="note-ai" data-k="quiz">${icon('spark', 14)} Practice Quiz</button>
                <button class="btn sm" data-act="note-img-add" title="Attach image from camera or gallery">${icon('plus', 14)} Add Image</button>
                <input type="file" id="note-img-input" accept="image/*" multiple style="display:none">
                <span class="grow"></span>
                <span class="mut xs" id="notesavetag">Saved</span>
              </div>
              ${(curNote.images && curNote.images.length) ? `
                <div style="margin-top:12px">
                  <div class="mut xs" style="margin-bottom:8px;font-weight:600">Attached images (${curNote.images.length})</div>
                  <div style="display:flex;flex-wrap:wrap;gap:10px" id="note-img-gallery">
                    ${curNote.images.map(img => `
                      <div style="position:relative;width:110px;border:1px solid var(--line);border-radius:var(--radius-md);overflow:hidden;background:var(--bg-subtle)">
                        <img src="${esc(img.dataUrl)}" alt="${esc(img.name || 'Note image')}" style="width:100%;height:80px;object-fit:cover;display:block;cursor:pointer" data-act="note-img-view" data-id="${esc(img.id)}" title="Click to view">
                        <div style="padding:4px 6px;font-size:10px;color:var(--ink-muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis">${esc(img.name || 'Image')}</div>
                        <button class="icon-btn" data-act="note-img-del" data-id="${esc(img.id)}" title="Remove image" style="position:absolute;top:4px;right:4px;width:24px;height:24px;background:rgba(0,0,0,0.55);border:none;color:#fff;border-radius:50%">
                          ${icon('x', 12)}
                        </button>
                      </div>
                    `).join('')}
                  </div>
                </div>
              ` : ''}
              <div id="noteai">${S.noteAI[curNote.id] ? `<div class="card" style="background:var(--bg-subtle);margin-top:10px">${md(S.noteAI[curNote.id].text)}</div>` : ''}</div>
            </div>
          `;
          $$('.note-item').forEach(btn => btn.classList.toggle('active', btn.dataset.id === id));
        }
      } else {
        render();
      }
      break;
    case 'note-pin': {
      const n = D.notes.find(x => x.id === S.noteId);
      if (n) {
        n.pinned = !n.pinned;
        save();
        render();
      }
      break;
    }
    case 'note-del':
      D.notes = D.notes.filter(x => x.id !== S.noteId);
      S.noteId = D.notes.length ? D.notes[0].id : null;
      save();
      render();
      toast('Note deleted.');
      break;
    case 'note-ai': noteAI(el.dataset.k); break;
    case 'note-img-add': {
      const input = document.getElementById('note-img-input');
      if (input) {
        input.value = '';
        input.click();
      }
      break;
    }
    case 'note-img-del': {
      const n = S.data.notes.find(x => x.id === S.noteId);
      if (!n || !n.images) break;
      n.images = n.images.filter(img => img.id !== id);
      n.updated = Date.now();
      save();
      // Re-open the note to refresh gallery
      const openBtn = document.querySelector(`.note-item[data-id="${S.noteId}"]`);
      if (openBtn) openBtn.click();
      else render();
      toast('Image removed.');
      break;
    }
    case 'note-img-view': {
      const n = S.data.notes.find(x => x.id === S.noteId);
      if (!n || !n.images) break;
      const img = n.images.find(i => i.id === id);
      if (!img) break;
      // Simple lightbox using a dialog
      const dlg = document.createElement('dialog');
      dlg.style.cssText = 'border:none;padding:0;border-radius:12px;max-width:95vw;max-height:90vh;background:var(--surface);box-shadow:var(--shadow-xl)';
      dlg.innerHTML = `
        <div style="padding:12px;display:flex;justify-content:space-between;align-items:center;border-bottom:1px solid var(--line)">
          <span style="font-weight:600;font-size:14px">${esc(img.name || 'Image')}</span>
          <button class="icon-btn" id="img-lightbox-close">${icon('x', 16)}</button>
        </div>
        <div style="padding:12px;text-align:center;max-height:75vh;overflow:auto">
          <img src="${esc(img.dataUrl)}" alt="" style="max-width:100%;max-height:70vh;border-radius:8px">
        </div>
      `;
      document.body.appendChild(dlg);
      dlg.showModal();
      const close = () => { dlg.close(); dlg.remove(); };
      dlg.querySelector('#img-lightbox-close').onclick = close;
      dlg.addEventListener('click', e => { if (e.target === dlg) close(); });
      break;
    }
    case 'chip': sendChat(el.dataset.q); break;
    case 'chat-clear':
      S.chat = [];
      store.set('cd:chat:' + S.user.id, []);
      renderChat();
      break;
    case 'voice': toggleVoice(); break;
    case 'tools-tab':
      S.toolsTab = el.dataset.t;
      if (el.dataset.t === 'cards') buildCards();
      render();
      break;
    case 'pomo-toggle': pomoToggle(); break;
    case 'pomo-reset': {
      const focusSec = Math.max(60, (S.pomo.customFocus || 25) * 60);
      S.pomo.run = false;
      S.pomo.mode = 'focus';
      S.pomo.left = focusSec;
      S.pomo.targetEndTime = null;
      // keep done count and custom durations
      updatePomoUI();
      if (S.view === 'tools' && S.toolsTab === 'study') {
        const el = $('#tools-content');
        if (el) el.innerHTML = toolsContent();
      }
      toast('Timer reset to focus block.');
      break;
    }
    case 'pomo-skip':
      pomoFinish();
      break;
    case 'pomo-apply': {
      if (S.pomo.run) {
        toast('Pause the timer before changing durations.');
        break;
      }
      const focusInput = document.getElementById('pomo-focus');
      const breakInput = document.getElementById('pomo-break');
      let f = focusInput ? parseInt(focusInput.value, 10) : 25;
      let b = breakInput ? parseInt(breakInput.value, 10) : 5;
      if (isNaN(f) || f < 1) f = 1;
      if (f > 180) f = 180;
      if (isNaN(b) || b < 1) b = 1;
      if (b > 60) b = 60;
      S.pomo.customFocus = f;
      S.pomo.customBreak = b;
      if (S.data && S.data.settings) {
        S.data.settings.focusMin = f;
        S.data.settings.breakMin = b;
        save();
      }
      // Reset current timer to the new focus length
      S.pomo.run = false;
      S.pomo.mode = 'focus';
      S.pomo.left = f * 60;
      S.pomo.targetEndTime = null;
      if (S.view === 'tools' && S.toolsTab === 'study') {
        const el = $('#tools-content');
        if (el) el.innerHTML = toolsContent();
      }
      toast(`Timer set to ${f} min focus / ${b} min break.`);
      break;
    }
    case 'pomo-presets': {
      if (S.pomo.run) break;
      // Cycle through common presets
      const presets = [
        { f: 25, b: 5,  label: 'Classic Pomodoro' },
        { f: 50, b: 10, label: 'Long Focus' },
        { f: 15, b: 5,  label: 'Short Sprint' },
        { f: 45, b: 15, label: 'Deep Work' },
        { f: 90, b: 20, label: 'Ultradian' }
      ];
      const curF = S.pomo.customFocus || 25;
      const curB = S.pomo.customBreak || 5;
      let idx = presets.findIndex(p => p.f === curF && p.b === curB);
      idx = (idx + 1) % presets.length;
      const next = presets[idx];
      S.pomo.customFocus = next.f;
      S.pomo.customBreak = next.b;
      if (S.data && S.data.settings) {
        S.data.settings.focusMin = next.f;
        S.data.settings.breakMin = next.b;
        save();
      }
      S.pomo.run = false;
      S.pomo.mode = 'focus';
      S.pomo.left = next.f * 60;
      S.pomo.targetEndTime = null;
      if (S.view === 'tools' && S.toolsTab === 'study') {
        const el = $('#tools-content');
        if (el) el.innerHTML = toolsContent();
      }
      toast(`${next.label}: ${next.f}/${next.b} min`);
      break;
    }
    case 'card-flip': {
      const c = $('#active-card');
      if (c) c.classList.toggle('flipped');
      break;
    }
    case 'card-next':
      S.cardI = (S.cardI + 1) % S.cards.length;
      render();
      break;
    case 'card-prev':
      S.cardI = (S.cardI - 1 + S.cards.length) % S.cards.length;
      render();
      break;
    case 'card-rebuild':
      buildCards();
      render();
      toast('Flashcard deck rebuilt from notes.');
      break;
    case 'g-add':
      D.grades.push({ id: uid(), subject: D.subjects[0] ? D.subjects[0].id : '', credits: 3, grade: 'A' });
      save();
      render();
      break;
    case 'g-del':
      D.grades = D.grades.filter(g => g.id !== id);
      save();
      render();
      break;
    case 'cmd-open': openCmd(); break;
    case 'cmd-go': runCmd(el.dataset.cmd, el.dataset.arg); break;
    case 'export': exportData(); break;
    case 'import': pickImport(); break;
    case 'clear-key':
      if (S.data && S.data.settings) {
        S.data.settings.geminiKey = '';
        save();
        const keyInput = document.getElementById('st_key');
        if (keyInput) keyInput.value = '';
        toast('Gemini API key cleared.');
        // Refresh modal if open
        const modal = document.getElementById('modal');
        if (modal && modal.open) profileModal();
      }
      break;
    case 'n-dismiss':
      D.dismissed.push(id);
      save();
      render();
      break;
    case 'n-clear':
      notifs().forEach(n => D.dismissed.push(n.id));
      save();
      render();
      break;
    case 'm-cancel': $('#modal').close(); break;
    case 'm-del':
      if (modalDelCallback) {
        modalDelCallback();
        $('#modal').close();
      }
      break;
  }
});

/* Flashcard Keyboard Accessibility */
document.addEventListener('keydown', e => {
  if (e.target && e.target.id === 'active-card') {
    if (e.key === 'Enter' || e.key === ' ') {
      e.preventDefault();
      e.target.classList.toggle('flipped');
    }
  }
});

/* Chat Submit & Input Events */
document.addEventListener('submit', e => {
  if (e.target.id === 'authform') { e.preventDefault(); doAuth(); }
  if (e.target.id === 'chatform') {
    e.preventDefault();
    if (S.busy) {
      toast('AI is replying, please wait a moment...');
      return;
    }
    const i = $('#chatin');
    const val = (i && i.value) || '';
    if (!val.trim()) return;
    i.value = '';
    i.style.height = 'auto';
    sendChat(val);
  }
  if (e.target.id === 'lookform') {
    e.preventDefault();
    const q = ($('#lookq') && $('#lookq').value || '').trim();
    if (!q) return;
    S.lookupQ = q;
    S.lookupBusy = true;
    S.lookup = null;
    S.wiki = null;
    render();
    Promise.all([
      API.dict(q).then(res => { S.lookup = res; }).catch(() => {}),
      API.wiki(q).then(res => { S.wiki = res; }).catch(() => {})
    ]).finally(() => {
      S.lookupBusy = false;
      render();
    });
  }
});

/* Command Palette Keyboard Shortcuts */
document.addEventListener('keydown', e => {
  if ((e.ctrlKey || e.metaKey) && e.key.toLowerCase() === 'k') {
    e.preventDefault();
    if (S.user) openCmd();
    return;
  }
  // Quick actions when not typing in an input
  if (S.user && !['INPUT','TEXTAREA','SELECT'].includes(e.target.tagName)) {
    if (e.key.toLowerCase() === 'n' && S.view === 'notes') {
      e.preventDefault();
      // Trigger new note
      const btn = document.querySelector('[data-act="note-new"]');
      if (btn) btn.click();
    }
    if (e.key.toLowerCase() === 't' && (S.view === 'tasks' || S.view === 'home')) {
      e.preventDefault();
      const btn = document.querySelector('[data-act="as-add"]');
      if (btn) btn.click();
    }
  }
  if (e.key === 'Escape') {
    const c = $('#cmd');
    if (c && c.open) c.close();
    const s = $('#more-sheet');
    if (s && s.classList.contains('open')) s.classList.remove('open');
  }
  if (e.target.id === 'cmdq') {
    if (e.key === 'ArrowDown') { e.preventDefault(); S.cmdI++; paintCmd(); }
    if (e.key === 'ArrowUp') { e.preventDefault(); S.cmdI--; paintCmd(); }
    if (e.key === 'Enter') {
      e.preventDefault();
      const items = cmdItems($('#cmdq').value);
      const it = items[S.cmdI];
      if (it) runCmd(it.cmd, it.arg);
    }
  }
  if (e.target.id === 'chatin' && e.key === 'Enter' && !e.shiftKey) {
    e.preventDefault();
    $('#chatform').requestSubmit();
  }
});

/* Textarea Autosize & Granular Inputs */
let noteFilterDebounce = null;
document.addEventListener('input', e => {
  const id = e.target.id;
  if (id === 'chatin') {
    e.target.style.height = 'auto';
    e.target.style.height = Math.min(e.target.scrollHeight, 140) + 'px';
  }
  if (id === 'cmdq') { S.cmdI = 0; paintCmd(); }
  if (id === 'noteq') {
    S.noteQ = e.target.value;
    clearTimeout(noteFilterDebounce);
    noteFilterDebounce = setTimeout(() => {
      const box = $('#noteslist');
      if (box) box.innerHTML = renderNoteItemsHtml();
    }, 120);
  }
  if (id === 'ntitle' || id === 'nbody') {
    const n = S.data.notes.find(x => x.id === S.noteId);
    if (!n) return;
    if (id === 'ntitle') n.title = e.target.value;
    else n.body = e.target.value;
    n.updated = Date.now();
    const tag = $('#notesavetag');
    if (tag) {
      tag.textContent = 'Saving…';
      tag.style.color = 'var(--warn)';
    }
    saveSoon();
    setTimeout(() => {
      if (tag) {
        tag.textContent = 'Saved';
        tag.style.color = 'var(--ok)';
        setTimeout(() => { if (tag) tag.style.color = ''; }, 1200);
      }
    }, 350);
  }
});

document.addEventListener('change', e => {
  const act = e.target.dataset.act, id = e.target.dataset.id;

  // Image attachment for notes
  if (e.target.id === 'note-img-input' && e.target.files && e.target.files.length) {
    const n = S.data.notes.find(x => x.id === S.noteId);
    if (!n) return;
    if (!Array.isArray(n.images)) n.images = [];
    const files = Array.from(e.target.files).slice(0, 8); // max 8 at a time
    let pending = files.length;
    toast(`Adding ${files.length} image${files.length > 1 ? 's' : ''}…`);
    files.forEach(async (file) => {
      try {
        // Soft limit: skip very large originals (>12 MB)
        if (file.size > 12 * 1024 * 1024) {
          toast(`Skipped ${file.name} (too large)`);
        } else {
          const dataUrl = await fileToCompressedDataUrl(file);
          // Rough size check after compression (~1.5 MB limit per image)
          if (dataUrl.length > 2 * 1024 * 1024) {
            toast(`Skipped ${file.name} (still too large after compression)`);
          } else {
            n.images.push({
              id: uid(),
              name: file.name || 'Image',
              dataUrl,
              added: Date.now()
            });
          }
        }
      } catch (err) {
        toast('Could not process one of the images.');
      } finally {
        pending--;
        if (pending === 0) {
          n.updated = Date.now();
          save();
          // Refresh editor
          const openBtn = document.querySelector(`.note-item[data-id="${S.noteId}"]`);
          if (openBtn) openBtn.click();
          else render();
          toast('Images attached to note.');
        }
      }
    });
    e.target.value = '';
    return;
  }

  if (e.target.id === 'nsub') {
    const n = S.data.notes.find(x => x.id === S.noteId);
    if (n) { n.subject = e.target.value; n.updated = Date.now(); save(); }
  }
  if (act && S.data) {
    const g = (S.data.grades || []).find(x => x.id === id);
    if (act === 'g-sub' && g) {
      g.subject = e.target.value;
      const matchS = S.data.subjects.find(s => s.id === g.subject);
      if (matchS && matchS.credits) g.credits = matchS.credits;
      save();
      render();
    }
    if (act === 'g-cr' && g) { g.credits = parseInt(e.target.value, 10) || 1; save(); render(); }
    if (act === 'g-gr' && g) { g.grade = e.target.value; save(); render(); }
  }
});

/* Modal Drag-Select Backdrop Fix */
const modalDialog = $('#modal');
modalDialog.addEventListener('mousedown', e => {
  backdropMouseDown = (e.target === modalDialog);
});
modalDialog.addEventListener('click', e => {
  if (backdropMouseDown && e.target === modalDialog) modalDialog.close();
});

const cmdDialog = $('#cmd');
cmdDialog.addEventListener('click', e => { if (e.target === cmdDialog) cmdDialog.close(); });

/* ==========================================================================
   INITIALIZATION
   ========================================================================== */
(function boot() {
  applyTheme();
  const sid = store.get('cd:session', null);
  const u = getUsers().find(x => x.id === sid);
  if (u) {
    S.user = u;
    S.data = loadData(u.id);
    S.chat = store.get('cd:chat:' + u.id, []);
    const st = S.data.settings || {};
    S.pomo.customFocus = Math.max(1, Math.min(180, +(st.focusMin || 25)));
    S.pomo.customBreak = Math.max(1, Math.min(60, +(st.breakMin || 5)));
    if (!S.pomo.run) {
      S.pomo.left = S.pomo.customFocus * 60;
      S.pomo.mode = 'focus';
    }
    applyTheme();
    refreshCampus();
    buildCards();
  }
  render();
  setInterval(tick, 1000);
})();

})();
</script>
</body>
</html>

