<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Roshan Hacker — Cybersecurity Researcher</title>

<!-- Motion Library for Spring Animations -->
<script src="https://cdn.jsdelivr.net/npm/motion@latest/dist/motion.js" defer></script>

<style>
  /* ═══════════════════════════════════════════════════════════════
     APPLE DESIGN SYSTEM — Core Variables
     ═══════════════════════════════════════════════════════════════ */
  :root {
    /* Typography — Apple's optical sizing system */
    --font-system: system-ui, -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'SF Pro Text', 'Helvetica Neue', Arial, sans-serif;
    --font-mono: 'SF Mono', SFMono-Regular, ui-monospace, 'Cascadia Code', 'Source Code Pro', Menlo, monospace;

    /* Colors — Dark mode (hacker aesthetic) */
    --bg-primary: #0a0a0c;
    --bg-secondary: #111114;
    --bg-tertiary: #1a1a1f;
    --surface-glass: rgba(255, 255, 255, 0.03);
    --surface-glass-hover: rgba(255, 255, 255, 0.06);
    --border-subtle: rgba(255, 255, 255, 0.06);
    --border-glass: rgba(255, 255, 255, 0.08);

    /* Text */
    --text-primary: rgba(255, 255, 255, 0.92);
    --text-secondary: rgba(255, 255, 255, 0.55);
    --text-tertiary: rgba(255, 255, 255, 0.35);

    /* Accent — Cybersecurity Blue */
    --accent: #0a84ff;
    --accent-glow: rgba(10, 132, 255, 0.15);
    --accent-glow-strong: rgba(10, 132, 255, 0.3);

    /* Green — Success/Hack */
    --green: #30d158;
    --green-glow: rgba(48, 209, 88, 0.15);

    /* Red — Warning */
    --red: #ff453a;
    --red-glow: rgba(255, 69, 58, 0.15);

    /* Orange — Energy */
    --orange: #ff9f0a;
    --orange-glow: rgba(255, 159, 10, 0.15);

    /* Spacing — Apple's 4px grid */
    --space-xs: 0.25rem;
    --space-sm: 0.5rem;
    --space-md: 1rem;
    --space-lg: 1.5rem;
    --space-xl: 2rem;
    --space-2xl: 3rem;
    --space-3xl: 4rem;

    /* Radii — Apple's continuous corner radius */
    --radius-sm: 8px;
    --radius-md: 12px;
    --radius-lg: 16px;
    --radius-xl: 20px;
    --radius-2xl: 24px;

    /* Shadows — Depth hierarchy */
    --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.3);
    --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.4);
    --shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.5);
    --shadow-xl: 0 16px 48px rgba(0, 0, 0, 0.6);

    /* Materials — Translucency */
    --blur-sm: blur(12px);
    --blur-md: blur(20px);
    --blur-lg: blur(40px);
  }

  /* ═══════════════════════════════════════════════════════════════
     RESET & BASE
     ═══════════════════════════════════════════════════════════════ */
  *, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  html {
    scroll-behavior: smooth;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  body {
    font-family: var(--font-system);
    font-size: 16px;
    line-height: 1.5;
    color: var(--text-primary);
    background: var(--bg-primary);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ═══════════════════════════════════════════════════════════════
     AMBIENT BACKGROUND — Subtle gradient animation
     ═══════════════════════════════════════════════════════════════ */
  .ambient {
    position: fixed;
    inset: 0;
    z-index: -1;
    overflow: hidden;
    pointer-events: none;
  }

  .ambient::before {
    content: '';
    position: absolute;
    width: 800px;
    height: 800px;
    top: -200px;
    right: -200px;
    background: radial-gradient(circle, var(--accent-glow) 0%, transparent 70%);
    animation: ambientFloat 20s ease-in-out infinite;
  }

  .ambient::after {
    content: '';
    position: absolute;
    width: 600px;
    height: 600px;
    bottom: -100px;
    left: -100px;
    background: radial-gradient(circle, var(--green-glow) 0%, transparent 70%);
    animation: ambientFloat 25s ease-in-out infinite reverse;
  }

  @keyframes ambientFloat {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(30px, -30px) scale(1.05); }
    66% { transform: translate(-20px, 20px) scale(0.95); }
  }

  /* ═══════════════════════════════════════════════════════════════
     CONTAINER
     ═══════════════════════════════════════════════════════════════ */
  .container {
    max-width: 720px;
    margin: 0 auto;
    padding: var(--space-xl) var(--space-lg);
  }

  /* ═══════════════════════════════════════════════════════════════
     HERO SECTION — Frosted Glass Material
     ═══════════════════════════════════════════════════════════════ */
  .hero {
    position: relative;
    padding: var(--space-3xl) var(--space-2xl);
    margin-bottom: var(--space-3xl);
    border-radius: var(--radius-2xl);
    background: var(--surface-glass);
    backdrop-filter: var(--blur-md);
    -webkit-backdrop-filter: var(--blur-md);
    border: 1px solid var(--border-glass);
    box-shadow: var(--shadow-lg);
    overflow: hidden;
    opacity: 0;
    transform: translateY(20px);
    animation: heroReveal 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    animation-delay: 0.1s;
  }

  @keyframes heroReveal {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  /* Material light-catching edge */
  .hero::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
  }

  /* Gradient accent line */
  .hero::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 120px;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--green));
    border-radius: 2px;
    opacity: 0.6;
  }

  .hero-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: var(--space-lg);
  }

  /* Avatar — Spring-animated */
  .avatar-wrapper {
    position: relative;
    width: 120px;
    height: 120px;
    border-radius: 50%;
    cursor: pointer;
    transition: transform 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
  }

  .avatar-wrapper:hover {
    transform: scale(1.05);
  }

  .avatar-wrapper:active {
    transform: scale(0.97);
    transition-duration: 0.1s;
  }

  .avatar {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 2px solid var(--border-glass);
    box-shadow: 0 0 0 4px var(--bg-primary), 0 0 0 5px var(--border-subtle);
    object-fit: cover;
  }

  /* Online indicator */
  .avatar-status {
    position: absolute;
    bottom: 4px;
    right: 4px;
    width: 16px;
    height: 16px;
    background: var(--green);
    border-radius: 50%;
    border: 3px solid var(--bg-primary);
    box-shadow: 0 0 8px var(--green-glow);
  }

  /* Name — Apple's display typography */
  .hero-name {
    font-size: clamp(1.75rem, 4vw, 2.25rem);
    font-weight: 700;
    letter-spacing: -0.025em;
    line-height: 1.1;
    color: var(--text-primary);
  }

  /* Bio — Secondary text */
  .hero-bio {
    font-size: 1rem;
    color: var(--text-secondary);
    max-width: 480px;
    line-height: 1.6;
  }

  .hero-bio .highlight {
    color: var(--accent);
    font-weight: 500;
  }

  /* Status badge */
  .status-badge {
    display: inline-flex;
    align-items: center;
    gap: var(--space-sm);
    padding: var(--space-xs) var(--space-md);
    border-radius: 100px;
    background: var(--surface-glass);
    border: 1px solid var(--border-glass);
    font-size: 0.8rem;
    color: var(--text-secondary);
    backdrop-filter: var(--blur-sm);
    -webkit-backdrop-filter: var(--blur-sm);
  }

  .status-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--green);
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; box-shadow: 0 0 0 0 var(--green-glow); }
    50% { opacity: 0.7; box-shadow: 0 0 0 4px transparent; }
  }

  /* ═══════════════════════════════════════════════════════════════
     SECTION HEADERS
     ═══════════════════════════════════════════════════════════════ */
  .section {
    margin-bottom: var(--space-3xl);
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: var(--space-sm);
    margin-bottom: var(--space-lg);
    padding-bottom: var(--space-sm);
    border-bottom: 1px solid var(--border-subtle);
  }

  .section-icon {
    font-size: 1.1rem;
  }

  .section-title {
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--text-tertiary);
  }

  /* ═══════════════════════════════════════════════════════════════
     PROJECT CARDS — Frosted Glass + Spring Hover
     ═══════════════════════════════════════════════════════════════ */
  .projects-grid {
    display: grid;
    gap: var(--space-md);
  }

  .project-card {
    position: relative;
    padding: var(--space-xl);
    border-radius: var(--radius-lg);
    background: var(--surface-glass);
    backdrop-filter: var(--blur-sm);
    -webkit-backdrop-filter: var(--blur-sm);
    border: 1px solid var(--border-glass);
    box-shadow: var(--shadow-sm);
    cursor: pointer;
    text-decoration: none;
    color: inherit;
    display: block;
    overflow: hidden;
    transition: transform 0.5s cubic-bezier(0.34, 1.56, 0.64, 1),
                box-shadow 0.5s cubic-bezier(0.34, 1.56, 0.64, 1),
                background 0.3s ease;
    opacity: 0;
    transform: translateY(20px);
    animation: cardReveal 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  }

  .project-card:nth-child(1) { animation-delay: 0.3s; }
  .project-card:nth-child(2) { animation-delay: 0.4s; }
  .project-card:nth-child(3) { animation-delay: 0.5s; }

  @keyframes cardReveal {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.08), transparent);
  }

  .project-card:hover {
    transform: translateY(-4px) scale(1.01);
    box-shadow: var(--shadow-xl);
    background: var(--surface-glass-hover);
  }

  .project-card:active {
    transform: translateY(-2px) scale(0.99);
    transition-duration: 0.15s;
  }

  .project-card.featured {
    border-color: var(--accent);
    background: linear-gradient(135deg, var(--accent-glow) 0%, var(--surface-glass) 100%);
  }

  .project-card.featured::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--green));
  }

  .project-header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: var(--space-md);
    margin-bottom: var(--space-md);
  }

  .project-icon {
    width: 48px;
    height: 48px;
    border-radius: var(--radius-md);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    background: var(--accent-glow);
    border: 1px solid rgba(10, 132, 255, 0.2);
    flex-shrink: 0;
  }

  .project-arrow {
    color: var(--text-tertiary);
    font-size: 1.2rem;
    transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  }

  .project-card:hover .project-arrow {
    transform: translate(4px, -4px);
    color: var(--accent);
  }

  .project-name {
    font-size: 1.1rem;
    font-weight: 600;
    letter-spacing: -0.01em;
    color: var(--text-primary);
    margin-bottom: var(--space-xs);
  }

  .project-desc {
    font-size: 0.9rem;
    color: var(--text-secondary);
    line-height: 1.5;
    margin-bottom: var(--space-md);
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: var(--space-xs);
  }

  .project-tag {
    padding: 2px 10px;
    border-radius: 100px;
    font-size: 0.7rem;
    font-weight: 500;
    background: var(--surface-glass);
    border: 1px solid var(--border-glass);
    color: var(--text-secondary);
    transition: all 0.3s ease;
  }

  .project-card:hover .project-tag {
    background: var(--accent-glow);
    border-color: rgba(10, 132, 255, 0.2);
    color: var(--accent);
  }

  .project-tag.lang {
    background: rgba(10, 132, 255, 0.1);
    color: var(--accent);
    border-color: rgba(10, 132, 255, 0.2);
  }

  .project-tag.lang.python { background: rgba(55, 118, 171, 0.15); color: #3776ab; border-color: rgba(55, 118, 171, 0.25); }
  .project-tag.lang.bash { background: rgba(78, 170, 37, 0.15); color: #4eaa25; border-color: rgba(78, 170, 37, 0.25); }

  /* ═══════════════════════════════════════════════════════════════
     TECH STACK — Frosted Glass Chips
     ═══════════════════════════════════════════════════════════════ */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: var(--space-sm);
  }

  .tech-chip {
    display: inline-flex;
    align-items: center;
    gap: var(--space-xs);
    padding: var(--space-sm) var(--space-md);
    border-radius: 100px;
    background: var(--surface-glass);
    backdrop-filter: var(--blur-sm);
    -webkit-backdrop-filter: var(--blur-sm);
    border: 1px solid var(--border-glass);
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--text-secondary);
    cursor: default;
    transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    opacity: 0;
    transform: translateY(10px);
    animation: chipReveal 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  }

  .tech-chip:nth-child(1) { animation-delay: 0.5s; }
  .tech-chip:nth-child(2) { animation-delay: 0.55s; }
  .tech-chip:nth-child(3) { animation-delay: 0.6s; }
  .tech-chip:nth-child(4) { animation-delay: 0.65s; }
  .tech-chip:nth-child(5) { animation-delay: 0.7s; }
  .tech-chip:nth-child(6) { animation-delay: 0.75s; }
  .tech-chip:nth-child(7) { animation-delay: 0.8s; }
  .tech-chip:nth-child(8) { animation-delay: 0.85s; }

  @keyframes chipReveal {
    to { opacity: 1; transform: translateY(0); }
  }

  .tech-chip:hover {
    transform: translateY(-2px) scale(1.05);
    background: var(--surface-glass-hover);
    border-color: rgba(255, 255, 255, 0.12);
    box-shadow: var(--shadow-md);
  }

  .tech-chip:active {
    transform: scale(0.95);
    transition-duration: 0.1s;
  }

  .tech-chip .icon {
    font-size: 1rem;
  }

  .tech-chip.color-blue { border-color: rgba(10, 132, 255, 0.3); color: var(--accent); }
  .tech-chip.color-green { border-color: rgba(48, 209, 88, 0.3); color: var(--green); }
  .tech-chip.color-red { border-color: rgba(255, 69, 58, 0.3); color: var(--red); }
  .tech-chip.color-orange { border-color: rgba(255, 159, 10, 0.3); color: var(--orange); }

  /* ═══════════════════════════════════════════════════════════════
     STATS — Animated Counters
     ═══════════════════════════════════════════════════════════════ */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: var(--space-md);
  }

  .stat-card {
    padding: var(--space-lg);
    border-radius: var(--radius-lg);
    background: var(--surface-glass);
    backdrop-filter: var(--blur-sm);
    -webkit-backdrop-filter: var(--blur-sm);
    border: 1px solid var(--border-glass);
    text-align: center;
    transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    opacity: 0;
    transform: translateY(15px);
    animation: statReveal 0.5s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  }

  .stat-card:nth-child(1) { animation-delay: 0.6s; }
  .stat-card:nth-child(2) { animation-delay: 0.7s; }
  .stat-card:nth-child(3) { animation-delay: 0.8s; }

  @keyframes statReveal {
    to { opacity: 1; transform: translateY(0); }
  }

  .stat-card:hover {
    transform: translateY(-3px) scale(1.02);
    box-shadow: var(--shadow-lg);
    background: var(--surface-glass-hover);
  }

  .stat-value {
    font-size: 1.75rem;
    font-weight: 700;
    letter-spacing: -0.03em;
    line-height: 1;
    margin-bottom: var(--space-xs);
  }

  .stat-value.accent { color: var(--accent); }
  .stat-value.green { color: var(--green); }
  .stat-value.orange { color: var(--orange); }

  .stat-label {
    font-size: 0.7rem;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--text-tertiary);
  }

  /* ═══════════════════════════════════════════════════════════════
     GITHUB STATS — Embedded Cards
     ═══════════════════════════════════════════════════════════════ */
  .stats-embed {
    border-radius: var(--radius-lg);
    overflow: hidden;
    border: 1px solid var(--border-glass);
    box-shadow: var(--shadow-sm);
    opacity: 0;
    animation: fadeIn 0.6s ease forwards;
    animation-delay: 0.9s;
  }

  @keyframes fadeIn {
    to { opacity: 1; }
  }

  .stats-embed img {
    width: 100%;
    display: block;
  }

  /* ═══════════════════════════════════════════════════════════════
     MOTIVATION — Typing Animation
     ═══════════════════════════════════════════════════════════════ */
  .motivation {
    text-align: center;
    padding: var(--space-3xl) var(--space-lg);
    opacity: 0;
    animation: fadeIn 0.8s ease forwards;
    animation-delay: 1s;
  }

  .motivation-quote {
    font-size: 0.9rem;
    font-style: italic;
    color: var(--text-tertiary);
    margin-bottom: var(--space-xl);
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
  }

  .typing-container {
    display: flex;
    justify-content: center;
  }

  .typing-text {
    font-family: var(--font-mono);
    font-size: clamp(0.7rem, 2vw, 0.85rem);
    color: var(--accent);
    letter-spacing: 0.02em;
  }

  .typing-cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent);
    margin-left: 2px;
    animation: blink 1s step-end infinite;
    vertical-align: text-bottom;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  /* ═══════════════════════════════════════════════════════════════
     SOCIAL LINKS
     ═══════════════════════════════════════════════════════════════ */
  .social-links {
    display: flex;
    justify-content: center;
    gap: var(--space-md);
    margin-top: var(--space-xl);
    opacity: 0;
    animation: fadeIn 0.6s ease forwards;
    animation-delay: 1.1s;
  }

  .social-link {
    width: 44px;
    height: 44px;
    border-radius: var(--radius-md);
    background: var(--surface-glass);
    border: 1px solid var(--border-glass);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--text-secondary);
    text-decoration: none;
    font-size: 1.2rem;
    transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
  }

  .social-link:hover {
    transform: translateY(-3px) scale(1.1);
    background: var(--accent-glow);
    border-color: rgba(10, 132, 255, 0.3);
    color: var(--accent);
    box-shadow: 0 4px 16px var(--accent-glow);
  }

  .social-link:active {
    transform: scale(0.9);
    transition-duration: 0.1s;
  }

  /* ═══════════════════════════════════════════════════════════════
     FOOTER
     ═══════════════════════════════════════════════════════════════ */
  .footer {
    text-align: center;
    padding: var(--space-2xl) 0 var(--space-lg);
    border-top: 1px solid var(--border-subtle);
    opacity: 0;
    animation: fadeIn 0.6s ease forwards;
    animation-delay: 1.2s;
  }

  .footer-text {
    font-size: 0.75rem;
    color: var(--text-tertiary);
    letter-spacing: 0.02em;
  }

  .footer-text .heart {
    color: var(--red);
    display: inline-block;
    animation: heartbeat 1.5s ease-in-out infinite;
  }

  @keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.15); }
  }

  /* ═══════════════════════════════════════════════════════════════
     SCROLL EDGE EFFECT — Gradient mask
     ═══════════════════════════════════════════════════════════════ */
  .scroll-fade-top {
    position: relative;
  }

  .scroll-fade-top::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 40px;
    background: linear-gradient(to bottom, var(--bg-primary), transparent);
    pointer-events: none;
    z-index: 1;
  }

  /* ═══════════════════════════════════════════════════════════════
     ACCESSIBILITY — Reduced Motion
     ═══════════════════════════════════════════════════════════════ */
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
      animation-duration: 0.01ms !important;
      animation-iteration-count: 1 !important;
      transition-duration: 0.01ms !important;
    }

    .ambient::before,
    .ambient::after {
      animation: none;
    }

    .avatar-status {
      animation: none;
    }

    .typing-cursor {
      animation: none;
    }

    .footer-text .heart {
      animation: none;
    }
  }

  @media (prefers-reduced-transparency: reduce) {
    .hero,
    .project-card,
    .tech-chip,
    .stat-card,
    .status-badge,
    .social-link {
      backdrop-filter: none;
      -webkit-backdrop-filter: none;
      background: var(--bg-tertiary);
    }
  }

  @media (prefers-contrast: more) {
    .hero,
    .project-card,
    .tech-chip,
    .stat-card {
      border-color: rgba(255, 255, 255, 0.2);
    }
  }

  /* ═══════════════════════════════════════════════════════════════
     RESPONSIVE
     ═══════════════════════════════════════════════════════════════ */
  @media (max-width: 640px) {
    .container {
      padding: var(--space-lg) var(--space-md);
    }

    .hero {
      padding: var(--space-2xl) var(--space-lg);
    }

    .stats-grid {
      grid-template-columns: repeat(3, 1fr);
      gap: var(--space-sm);
    }

    .stat-card {
      padding: var(--space-md);
    }

    .stat-value {
      font-size: 1.25rem;
    }
  }
</style>
</head>
<body>

<!-- Ambient Background -->
<div class="ambient"></div>

<div class="container">

  <!-- ═══════════════════════════════════════════════════════════════
       HERO SECTION
       ═══════════════════════════════════════════════════════════════ -->
  <section class="hero">
    <div class="hero-content">
      <div class="avatar-wrapper" role="img" aria-label="Roshan Hacker's avatar">
        <img
          class="avatar"
          src="https://avatars.githubusercontent.com/u/321773962?v=4"
          alt="Roshan Hacker"
          loading="eager"
        />
        <div class="avatar-status" aria-label="Online"></div>
      </div>

      <div>
        <h1 class="hero-name">Roshan Hacker</h1>
        <p class="hero-bio">
          <span class="highlight">Cybersecurity Researcher</span> &amp;
          Offensive Security Tools Developer. Building the future of
          <span class="highlight">ethical hacking</span>.
        </p>
      </div>

      <div class="status-badge">
        <span class="status-dot"></span>
        Building MSF Commander v4.0
      </div>
    </div>
  </section>

  <!-- ═══════════════════════════════════════════════════════════════
       PROJECTS
       ═══════════════════════════════════════════════════════════════ -->
  <section class="section">
    <div class="section-header">
      <span class="section-icon">&#9876;</span>
      <span class="section-title">Projects</span>
    </div>

    <div class="projects-grid">
      <!-- Featured Project -->
      <a
        href="https://github.com/dark-hacker-error/msf-commander"
        class="project-card featured"
        target="_blank"
        rel="noopener noreferrer"
      >
        <div class="project-header">
          <div class="project-icon">&#9876;</div>
          <span class="project-arrow">&#8599;</span>
        </div>
        <h3 class="project-name">MSF Commander v4.0</h3>
        <p class="project-desc">
          Complete Offensive Security Arsenal. Auto-install, mobile friendly,
          24+ payloads. The most powerful Metasploit Framework tool for
          penetration testers.
        </p>
        <div class="project-tags">
          <span class="project-tag lang python">Python</span>
          <span class="project-tag">Metasploit</span>
          <span class="project-tag">Penetration Testing</span>
          <span class="project-tag">Android</span>
          <span class="project-tag">Termux</span>
        </div>
      </a>

      <!-- Future Project Placeholder -->
      <div class="project-card" style="opacity: 0.5; cursor: default;">
        <div class="project-header">
          <div class="project-icon" style="background: var(--green-glow); border-color: rgba(48, 209, 88, 0.2);">&#128274;</div>
        </div>
        <h3 class="project-name">More Tools Coming Soon</h3>
        <p class="project-desc">
          Additional offensive security tools and utilities in development.
          Stay tuned for network scanners, vulnerability assessors, and more.
        </p>
        <div class="project-tags">
          <span class="project-tag" style="opacity: 0.5;">In Development</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ═══════════════════════════════════════════════════════════════
       TECH STACK
       ═══════════════════════════════════════════════════════════════ -->
  <section class="section">
    <div class="section-header">
      <span class="section-icon">&#9881;</span>
      <span class="section-title">Tech Stack</span>
    </div>

    <div class="tech-grid">
      <div class="tech-chip color-blue">
        <span class="icon">&#128013;</span> Python
      </div>
      <div class="tech-chip color-green">
        <span class="icon">&#128187;</span> Bash
      </div>
      <div class="tech-chip color-orange">
        <span class="icon">&#128225;</span> Linux
      </div>
      <div class="tech-chip color-red">
        <span class="icon">&#9876;</span> Metasploit
      </div>
      <div class="tech-chip color-blue">
        <span class="icon">&#128241;</span> Termux
      </div>
      <div class="tech-chip color-green">
        <span class="icon">&#128737;</span> Kali Linux
      </div>
      <div class="tech-chip color-orange">
        <span class="icon">&#128269;</span> Nmap
      </div>
      <div class="tech-chip color-red">
        <span class="icon">&#128274;</span> Security
      </div>
    </div>
  </section>

  <!-- ═══════════════════════════════════════════════════════════════
       STATS
       ═══════════════════════════════════════════════════════════════ -->
  <section class="section">
    <div class="section-header">
      <span class="section-icon">&#128200;</span>
      <span class="section-title">Stats</span>
    </div>

    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-value accent" data-target="2">0</div>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-value green" data-target="24">0</div>
        <div class="stat-label">Payloads</div>
      </div>
      <div class="stat-card">
        <div class="stat-value orange" data-target="1">0</div>
        <div class="stat-label">Tools Built</div>
      </div>
    </div>
  </section>

  <!-- ═══════════════════════════════════════════════════════════════
       GITHUB STATS
       ═══════════════════════════════════════════════════════════════ -->
  <section class="section">
    <div class="section-header">
      <span class="section-icon">&#128202;</span>
      <span class="section-title">GitHub Stats</span>
    </div>

    <div class="stats-embed">
      <img
        src="https://github-readme-stats.vercel.app/api?username=dark-hacker-error&show_icons=true&theme=chartreuse-dark&hide_border=true&bg_color=transparent&title_color=0a84ff&icon_color=30d158&text_color=ffffff&ring_color=0a84ff"
        alt="GitHub Stats"
        loading="lazy"
      />
    </div>

    <div class="stats-embed" style="margin-top: var(--space-md);">
      <img
        src="https://github-readme-streak-stats.herokuapp.com/?user=dark-hacker-error&theme=chartreuse-dark&hide_border=true&background=transparent&ring=0a84ff&fire=30d158&currStreakLabel=ffffff&sideLabels=ffffff"
        alt="GitHub Streak"
        loading="lazy"
      />
    </div>
  </section>

  <!-- ═══════════════════════════════════════════════════════════════
       MOTIVATION
       ═══════════════════════════════════════════════════════════════ -->
  <section class="motivation">
    <p class="motivation-quote">
      "The only way to do great work is to love what you do."
    </p>
    <div class="typing-container">
      <span class="typing-text" id="typingText"></span>
      <span class="typing-cursor"></span>
    </div>

    <div class="social-links">
      <a
        href="https://github.com/dark-hacker-error"
        class="social-link"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="GitHub"
      >
        &#128187;
      </a>
      <a
        href="https://github.com/dark-hacker-error/msf-commander"
        class="social-link"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="MSF Commander"
      >
        &#9876;
      </a>
    </div>
  </section>

  <!-- ═══════════════════════════════════════════════════════════════
       FOOTER
       ═══════════════════════════════════════════════════════════════ -->
  <footer class="footer">
    <p class="footer-text">
      Built with <span class="heart">&#10084;</span> by Roshan Hacker &bull; Hack the Planet
    </p>
  </footer>

</div>

<!-- ═══════════════════════════════════════════════════════════════
     INTERACTIVE SCRIPTS
     ═══════════════════════════════════════════════════════════════ -->
<script>
document.addEventListener('DOMContentLoaded', () => {

  // ─── Typing Animation ───────────────────────────────────────
  const phrases = [
    'Cybersecurity Researcher',
    'Offensive Security Tools',
    'Python Developer',
    'Ethical Hacker',
    'Hack the Planet'
  ];

  const typingEl = document.getElementById('typingText');
  let phraseIndex = 0;
  let charIndex = 0;
  let isDeleting = false;
  let typingSpeed = 80;

  function type() {
    const currentPhrase = phrases[phraseIndex];

    if (isDeleting) {
      typingEl.textContent = currentPhrase.substring(0, charIndex - 1);
      charIndex--;
      typingSpeed = 40;
    } else {
      typingEl.textContent = currentPhrase.substring(0, charIndex + 1);
      charIndex++;
      typingSpeed = 80;
    }

    if (!isDeleting && charIndex === currentPhrase.length) {
      typingSpeed = 2000;
      isDeleting = true;
    } else if (isDeleting && charIndex === 0) {
      isDeleting = false;
      phraseIndex = (phraseIndex + 1) % phrases.length;
      typingSpeed = 500;
    }

    setTimeout(type, typingSpeed);
  }

  type();

  // ─── Stat Counter Animation ─────────────────────────────────
  const statValues = document.querySelectorAll('.stat-value[data-target]');

  const counterObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const el = entry.target;
        const target = parseInt(el.getAttribute('data-target'));
        let current = 0;
        const increment = target / 30;
        const timer = setInterval(() => {
          current += increment;
          if (current >= target) {
            el.textContent = target;
            clearInterval(timer);
          } else {
            el.textContent = Math.floor(current);
          }
        }, 50);
        counterObserver.unobserve(el);
      }
    });
  }, { threshold: 0.5 });

  statValues.forEach(el => counterObserver.observe(el));

  // ─── Spring Hover Effect on Cards ───────────────────────────
  if (typeof Motion !== 'undefined' && Motion.animate) {
    const cards = document.querySelectorAll('.project-card, .tech-chip, .stat-card, .social-link');

    cards.forEach(card => {
      card.addEventListener('pointerenter', () => {
        Motion.animate(card, {
          scale: card.classList.contains('project-card') ? 1.02 : 1.05,
          y: card.classList.contains('project-card') ? -4 : -2
        }, {
          type: 'spring',
          bounce: 0.2,
          duration: 0.5
        });
      });

      card.addEventListener('pointerleave', () => {
        Motion.animate(card, {
          scale: 1,
          y: 0
        }, {
          type: 'spring',
          bounce: 0,
          duration: 0.4
        });
      });
    });
  }

  // ─── Pointer-down instant feedback ──────────────────────────
  const interactives = document.querySelectorAll('a, button, .avatar-wrapper');

  interactives.forEach(el => {
    el.addEventListener('pointerdown', () => {
      el.style.transform = 'scale(0.97)';
      el.style.transition = 'transform 0.1s ease-out';
    });

    el.addEventListener('pointerup', () => {
      el.style.transform = '';
      el.style.transition = '';
    });

    el.addEventListener('pointerleave', () => {
      el.style.transform = '';
      el.style.transition = '';
    });
  });

});
</script>

</body>
</html>
