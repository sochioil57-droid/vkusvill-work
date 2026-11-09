[index 3.html](https://github.com/user-attachments/files/34578736/index.3.html)
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Работа и подработка — Доставка и Сборка заказов</title>
  <style>
/* ===================================================================
   ГЛОБАЛЬНЫЕ СТИЛИ И ПЕРЕМЕННЫЕ ДВУХ БРЕНДОВ
   =================================================================== */

:root {
  --radius-sm: 8px;
  --radius-md: 14px;
  --radius-lg: 20px;
  --radius-xl: 28px;
  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.08);
  --shadow-lg: 0 16px 40px rgba(0, 0, 0, 0.12);
  --font: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  --transition: all 0.25s cubic-bezier(0.16, 1, 0.3, 1);
}

/* ТЕМА: ВКУСВИЛЛ (Глубокий изумрудный зеленый, мятный, экологичный) */
body.theme-vkusvill {
  --primary: #006643;
  --primary-hover: #005034;
  --primary-dark: #003824;
  --primary-light: #eaf5ef;
  --primary-subtle: #d3ebd9;
  --accent: #10b981;
  --badge-bg: #006643;
  --badge-color: #ffffff;
  --bg-page: #f4f8f5;
  --bg-card: #ffffff;
  --text-main: #14221a;
  --text-muted: #4e6357;
  --border-color: #dbe7df;
  --slider-thumb: #006643;
  --header-bg: #ffffff;
  --hero-gradient: linear-gradient(135deg, #004d32 0%, #006643 60%, #028357 100%);
}

/* ТЕМА: ПЯТЁРОЧКА (Сочный зеленый #1FA84A, ярко-красный акцент #E31E24) */
body.theme-5ka {
  --primary: #1fa84a;
  --primary-hover: #188d3e;
  --primary-dark: #126e2f;
  --primary-light: #effaf2;
  --primary-subtle: #d2f2dc;
  --accent: #e31e24;
  --accent-hover: #bf141a;
  --badge-bg: #e31e24;
  --badge-color: #ffffff;
  --bg-page: #f5f6f8;
  --bg-card: #ffffff;
  --text-main: #1a1e24;
  --text-muted: #565d68;
  --border-color: #e2e5eb;
  --slider-thumb: #e31e24;
  --header-bg: #ffffff;
  --hero-gradient: linear-gradient(135deg, #136a30 0%, #1fa84a 55%, #22bb52 100%);
}

/* СБРОС И БАЗОВЫЕ НАСТРОЙКИ */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: var(--font);
  background-color: var(--bg-page);
  color: var(--text-main);
  line-height: 1.55;
  -webkit-font-smoothing: antialiased;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.container {
  width: 100%;
  max-width: 1080px;
  margin: 0 auto;
  padding: 0 16px;
}

/* ===================================================================
   ПАНЕЛЬ ПЕРЕКЛЮЧЕНИЯ БРЕНДОВ ВВЕРХУ (ДВА ЛЕНДИНГА)
   =================================================================== */

.brand-bar {
  background: #111827;
  color: #f3f4f6;
  padding: 10px 16px;
  font-size: 13px;
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
}

.brand-bar-inner {
  max-width: 1080px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 10px;
}

.brand-bar-label {
  color: #9ca3af;
  font-weight: 500;
}

.brand-toggle-group {
  display: inline-flex;
  background: #1f2937;
  padding: 3px;
  border-radius: 999px;
  border: 1px solid #374151;
}

.brand-btn {
  background: transparent;
  color: #d1d5db;
  border: none;
  padding: 6px 14px;
  border-radius: 999px;
  font-size: 13px;
  font-weight: 600;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  gap: 7px;
  transition: var(--transition);
}

.brand-btn:hover {
  color: #fff;
}

.brand-btn.active {
  background: #ffffff;
  color: #111827;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.25);
}

.dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  display: inline-block;
}

.dot-vv {
  background: #006643;
}

.dot-5ka {
  background: #e31e24;
}

.brand-bar-actions {
  display: flex;
  align-items: center;
  gap: 8px;
}

.export-btn,
.single-link {
  background: #374151;
  color: #e5e7eb;
  padding: 5px 11px;
  border-radius: 6px;
  text-decoration: none;
  font-size: 12px;
  border: none;
  cursor: pointer;
  transition: var(--transition);
  display: inline-flex;
  align-items: center;
  gap: 4px;
}

.export-btn:hover,
.single-link:hover {
  background: #4b5563;
  color: #fff;
}

/* ===================================================================
   ШАПКА (HEADER)
   =================================================================== */

.header {
  background: var(--header-bg);
  border-bottom: 1px solid var(--border-color);
  padding: 14px 0;
  transition: var(--transition);
}

.header-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo-box {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-icon {
  width: 44px;
  height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo-icon svg {
  width: 100%;
  height: 100%;
  display: block;
}

.brand-title {
  display: block;
  font-size: 20px;
  font-weight: 800;
  letter-spacing: -0.02em;
  color: var(--primary);
  line-height: 1.1;
}

.brand-badge {
  display: block;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--text-muted);
  font-weight: 600;
}

.header-phone {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 13px;
  font-weight: 600;
  color: var(--text-muted);
  background: var(--primary-light);
  padding: 6px 12px;
  border-radius: 20px;
}

.status-indicator {
  width: 8px;
  height: 8px;
  background: #10b981;
  border-radius: 50%;
  animation: pulseGreen 2s infinite;
}

@keyframes pulseGreen {
  0% { transform: scale(0.95); opacity: 0.8; }
  50% { transform: scale(1.25); opacity: 1; }
  100% { transform: scale(0.95); opacity: 0.8; }
}

/* ===================================================================
   ГЛАВНЫЙ ЭКРАН (HERO)
   =================================================================== */

.hero {
  background: var(--hero-gradient);
  color: #ffffff;
  padding: 48px 0 54px;
  position: relative;
  overflow: hidden;
  transition: var(--transition);
}

.hero::after {
  content: "";
  position: absolute;
  top: -50%;
  right: -20%;
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.12) 0%, rgba(255, 255, 255, 0) 70%);
  border-radius: 50%;
  pointer-events: none;
}

.hero-badge {
  display: inline-block;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(8px);
  padding: 6px 14px;
  border-radius: 999px;
  font-size: 13px;
  font-weight: 600;
  margin-bottom: 16px;
  border: 1px solid rgba(255, 255, 255, 0.25);
}

.hero-title {
  font-size: 32px;
  font-weight: 800;
  line-height: 1.2;
  margin-bottom: 14px;
  letter-spacing: -0.02em;
  max-width: 720px;
}

@media (min-width: 768px) {
  .hero-title {
    font-size: 42px;
  }
}

.hero-subtitle {
  font-size: 16px;
  line-height: 1.5;
  opacity: 0.95;
  margin-bottom: 26px;
  max-width: 640px;
}

.hero-highlights {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
  margin-bottom: 28px;
  max-width: 680px;
}

@media (min-width: 640px) {
  .hero-highlights {
    grid-template-columns: repeat(4, 1fr);
  }
}

.highlight-item {
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(6px);
  padding: 10px 12px;
  border-radius: var(--radius-md);
  border: 1px solid rgba(255, 255, 255, 0.15);
  display: flex;
  align-items: center;
  gap: 8px;
}

.hl-icon {
  font-size: 18px;
}

.hl-text {
  font-size: 13px;
  font-weight: 600;
  line-height: 1.25;
}

.hero-cta-row {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

/* ===================================================================
   КНОПКИ
   =================================================================== */

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 13px 24px;
  border-radius: var(--radius-md);
  font-size: 15px;
  font-weight: 700;
  text-decoration: none;
  cursor: pointer;
  border: none;
  transition: var(--transition);
  text-align: center;
}

.btn:active {
  transform: scale(0.98);
}

.btn-primary {
  background: var(--accent);
  color: #ffffff;
  box-shadow: 0 4px 14px rgba(0, 0, 0, 0.15);
}

body.theme-vkusvill .btn-primary {
  background: #10b981;
}

body.theme-vkusvill .btn-primary:hover {
  background: #059669;
}

body.theme-5ka .btn-primary {
  background: #e31e24;
}

body.theme-5ka .btn-primary:hover {
  background: #c41217;
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.2);
  color: #ffffff;
  border: 1px solid rgba(255, 255, 255, 0.35);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.3);
}

.btn-block {
  width: 100%;
}

.btn-sm {
  padding: 7px 14px;
  font-size: 13px;
  border-radius: var(--radius-sm);
}

.btn-danger {
  background: #ef4444;
  color: #ffffff;
}

.btn-danger:hover {
  background: #dc2626;
}

/* ===================================================================
   СЕКЦИИ И ЗАГОЛОВКИ
   =================================================================== */

.section {
  padding: 50px 0;
}

.section-head {
  text-align: center;
  margin-bottom: 34px;
}

.section-title {
  font-size: 26px;
  font-weight: 800;
  letter-spacing: -0.01em;
  margin-bottom: 8px;
  color: var(--text-main);
}

@media (min-width: 768px) {
  .section-title {
    font-size: 32px;
  }
}

.section-desc {
  font-size: 15px;
  color: var(--text-muted);
  max-width: 580px;
  margin: 0 auto;
}

/* ===================================================================
   КАРТОЧКИ ВАКАНСИЙ (3 ПРОФЕССИИ)
   =================================================================== */

.cards-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 20px;
}

@media (min-width: 768px) {
  .cards-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.job-card {
  background: var(--bg-card);
  border-radius: var(--radius-lg);
  border: 1px solid var(--border-color);
  padding: 24px;
  box-shadow: var(--shadow-sm);
  display: flex;
  flex-direction: column;
  transition: var(--transition);
  position: relative;
  overflow: hidden;
}

.job-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
  border-color: var(--primary);
}

.card-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 14px;
}

.card-icon {
  font-size: 36px;
  line-height: 1;
}

.card-badge {
  background: var(--primary-light);
  color: var(--primary);
  font-size: 12px;
  font-weight: 700;
  padding: 4px 10px;
  border-radius: 999px;
}

.card-title {
  font-size: 20px;
  font-weight: 800;
  margin-bottom: 8px;
  color: var(--text-main);
}

.card-income-box {
  background: var(--primary-light);
  border-radius: var(--radius-md);
  padding: 12px 14px;
  margin-bottom: 14px;
}

.card-income-label {
  font-size: 12px;
  color: var(--text-muted);
  font-weight: 600;
  display: block;
}

.card-income-val {
  font-size: 24px;
  font-weight: 800;
  color: var(--primary);
  line-height: 1.1;
}

.card-rate-sub {
  font-size: 12px;
  color: var(--text-muted);
  margin-top: 2px;
}

.card-desc {
  font-size: 14px;
  color: var(--text-muted);
  line-height: 1.45;
  margin-bottom: 16px;
  flex-grow: 1;
}

.card-bullets {
  list-style: none;
  margin-bottom: 18px;
}

.card-bullets li {
  font-size: 13px;
  color: var(--text-main);
  margin-bottom: 6px;
  display: flex;
  align-items: center;
  gap: 6px;
}

.card-bullets li::before {
  content: "✓";
  color: var(--primary);
  font-weight: 800;
}

.btn-card-select {
  width: 100%;
  background: var(--primary);
  color: #fff;
  padding: 11px;
  border-radius: var(--radius-md);
  font-weight: 700;
  font-size: 14px;
  border: none;
  cursor: pointer;
  transition: var(--transition);
  text-decoration: none;
  display: block;
  text-align: center;
}

.btn-card-select:hover {
  background: var(--primary-hover);
}

/* ===================================================================
   КАЛЬКУЛЯТОР ЗАРАБОТКА
   =================================================================== */

.calc-section {
  background: #ffffff;
  border-top: 1px solid var(--border-color);
  border-bottom: 1px solid var(--border-color);
}

.calc-wrapper {
  background: var(--bg-page);
  border-radius: var(--radius-xl);
  border: 1px solid var(--border-color);
  padding: 28px 20px;
}

@media (min-width: 768px) {
  .calc-wrapper {
    padding: 38px 32px;
  }
}

.calc-head {
  text-align: center;
  margin-bottom: 28px;
}

.calc-tag {
  display: inline-block;
  background: var(--primary-light);
  color: var(--primary);
  font-size: 13px;
  font-weight: 700;
  padding: 5px 14px;
  border-radius: 999px;
  margin-bottom: 10px;
}

.calc-title {
  font-size: 26px;
  font-weight: 800;
  margin-bottom: 6px;
}

.calc-desc {
  font-size: 14px;
  color: var(--text-muted);
}

.calc-body {
  display: grid;
  grid-template-columns: 1fr;
  gap: 28px;
}

@media (min-width: 820px) {
  .calc-body {
    grid-template-columns: 1.15fr 0.85fr;
    align-items: stretch;
  }
}

.calc-controls {
  display: flex;
  flex-direction: column;
  gap: 22px;
}

.control-group {
  background: #ffffff;
  border: 1px solid var(--border-color);
  border-radius: var(--radius-lg);
  padding: 18px;
}

.control-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
}

.control-label {
  font-size: 14px;
  font-weight: 700;
  color: var(--text-main);
}

.slider-val {
  background: var(--primary-light);
  color: var(--primary);
  padding: 3px 10px;
  border-radius: var(--radius-sm);
  font-weight: 800;
  font-size: 14px;
}

/* РОЛИ В КАЛЬКУЛЯТОРЕ */
.role-selector {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
  margin-top: 10px;
}

.role-opt-btn {
  background: #f3f4f6;
  border: 1.5px solid #e5e7eb;
  padding: 10px 8px;
  border-radius: var(--radius-md);
  cursor: pointer;
  text-align: center;
  font-size: 12px;
  font-weight: 700;
  color: var(--text-main);
  transition: var(--transition);
}

.role-opt-btn:hover {
  border-color: var(--primary);
}

.role-opt-btn.active {
  background: var(--primary-light);
  border-color: var(--primary);
  color: var(--primary);
}

.role-icon {
  font-size: 20px;
  display: block;
  margin-bottom: 4px;
}

/* ПОЛЗУНКИ (RANGE SLIDERS) */
.range-slider {
  width: 100%;
  height: 8px;
  border-radius: 4px;
  background: #e2e8f0;
  outline: none;
  -webkit-appearance: none;
  cursor: pointer;
}

.range-slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 24px;
  height: 24px;
  border-radius: 50%;
  background: var(--slider-thumb);
  cursor: pointer;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.25);
  transition: transform 0.15s ease;
}

.range-slider::-webkit-slider-thumb:hover {
  transform: scale(1.15);
}

.range-slider::-moz-range-thumb {
  width: 24px;
  height: 24px;
  border-radius: 50%;
  background: var(--slider-thumb);
  cursor: pointer;
  border: none;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.25);
}

.range-labels {
  display: flex;
  justify-content: space-between;
  margin-top: 8px;
  font-size: 11px;
  color: var(--text-muted);
  font-weight: 500;
}

/* КАРТОЧКА РЕЗУЛЬТАТА КАЛЬКУЛЯТОРА */
.calc-result-box {
  background: #ffffff;
  border: 2px solid var(--primary);
  border-radius: var(--radius-lg);
  padding: 24px;
  box-shadow: var(--shadow-md);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.result-badge {
  display: inline-block;
  background: var(--primary);
  color: #fff;
  font-size: 11px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  padding: 4px 10px;
  border-radius: 999px;
  align-self: flex-start;
  margin-bottom: 14px;
}

.result-row {
  margin-bottom: 12px;
}

.result-sublabel {
  font-size: 13px;
  color: var(--text-muted);
  display: block;
  margin-bottom: 2px;
}

.result-price {
  font-size: 26px;
  font-weight: 800;
  color: var(--text-main);
}

.primary-result {
  background: var(--primary-light);
  padding: 12px 14px;
  border-radius: var(--radius-md);
  margin-bottom: 16px;
}

.result-price-month {
  font-size: 34px;
  font-weight: 900;
  color: var(--primary);
  line-height: 1.1;
}

.result-details {
  display: flex;
  justify-content: space-between;
  border-top: 1px dashed var(--border-color);
  padding-top: 12px;
  margin-bottom: 16px;
  font-size: 13px;
}

.res-muted {
  color: var(--text-muted);
  margin-right: 4px;
}

.calc-note {
  font-size: 11px;
  color: var(--text-muted);
  margin-top: 10px;
  text-align: center;
  line-height: 1.35;
}

/* ===================================================================
   ФОРМА АНКЕТЫ (ЛИДОГЕНЕРАЦИЯ)
   =================================================================== */

.form-section {
  padding: 40px 0 60px;
}

.form-card {
  max-width: 680px;
  margin: 0 auto;
  background: var(--bg-card);
  border-radius: var(--radius-xl);
  border: 1px solid var(--border-color);
  padding: 32px 22px;
  box-shadow: var(--shadow-md);
}

@media (min-width: 640px) {
  .form-card {
    padding: 40px 34px;
  }
}

.form-header {
  text-align: center;
  margin-bottom: 26px;
}

.form-icon {
  font-size: 36px;
  margin-bottom: 6px;
}

.form-title {
  font-size: 24px;
  font-weight: 800;
  margin-bottom: 6px;
  color: var(--text-main);
}

.form-subtitle {
  font-size: 14px;
  color: var(--text-muted);
}

.form-row {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
  margin-bottom: 16px;
}

@media (min-width: 580px) {
  .form-row {
    grid-template-columns: 1fr 1fr;
  }
}

.form-field {
  margin-bottom: 16px;
}

.form-field label {
  display: block;
  font-size: 13px;
  font-weight: 700;
  margin-bottom: 6px;
  color: var(--text-main);
}

.form-field .req {
  color: #ef4444;
}

.form-field input,
.form-field select {
  width: 100%;
  padding: 12px 14px;
  border: 1.5px solid var(--border-color);
  border-radius: var(--radius-md);
  font-size: 15px;
  background: #ffffff;
  color: var(--text-main);
  outline: none;
  transition: var(--transition);
  font-family: inherit;
}

.form-field input:focus,
.form-field select:focus {
  border-color: var(--primary);
  box-shadow: 0 0 0 3px var(--primary-light);
}

.field-error {
  display: block;
  font-size: 12px;
  color: #dc2626;
  margin-top: 4px;
  min-height: 16px;
}

/* ЧЕКБОКС СОГЛАСИЯ */
.form-agreement {
  margin: 18px 0 22px;
}

.checkbox-container {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  cursor: pointer;
  font-size: 12px;
  color: var(--text-muted);
  line-height: 1.4;
}

.checkbox-container input {
  width: 18px;
  height: 18px;
  margin-top: 2px;
  accent-color: var(--primary);
}

.btn-submit {
  width: 100%;
  padding: 15px;
  font-size: 16px;
  border-radius: var(--radius-md);
}

.form-footer-guarantee {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 20px;
  padding-top: 18px;
  border-top: 1px solid var(--border-color);
  font-size: 12px;
  color: var(--text-muted);
  font-weight: 600;
}

/* ===================================================================
   ПРЕИМУЩЕСТВА (PERKS)
   =================================================================== */

.perks-section {
  background: #ffffff;
  border-top: 1px solid var(--border-color);
}

.perks-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 18px;
}

@media (min-width: 640px) {
  .perks-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 900px) {
  .perks-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.perk-card {
  background: var(--bg-page);
  border: 1px solid var(--border-color);
  border-radius: var(--radius-md);
  padding: 20px 18px;
  transition: var(--transition);
}

.perk-card:hover {
  transform: translateY(-2px);
  border-color: var(--primary);
}

.perk-icon {
  font-size: 28px;
  margin-bottom: 10px;
  display: inline-block;
}

.perk-title {
  font-size: 16px;
  font-weight: 800;
  margin-bottom: 6px;
}

.perk-desc {
  font-size: 13px;
  color: var(--text-muted);
  line-height: 1.45;
}

/* ===================================================================
   ФУТЕР
   =================================================================== */

.footer {
  background: #111827;
  color: #9ca3af;
  padding: 34px 0;
  font-size: 13px;
}

.footer-container {
  display: flex;
  flex-direction: column;
  gap: 16px;
  align-items: center;
  text-align: center;
}

@media (min-width: 640px) {
  .footer-container {
    flex-direction: row;
    justify-content: space-between;
    text-align: left;
  }
}

.footer-logo-text {
  font-size: 16px;
  font-weight: 800;
  color: #ffffff;
  display: block;
  margin-bottom: 4px;
}

.footer-copy {
  max-width: 460px;
  font-size: 12px;
  line-height: 1.4;
}

.footer-links {
  display: flex;
  gap: 12px;
}

.text-link {
  background: transparent;
  color: #d1d5db;
  border: none;
  font-size: 12px;
  cursor: pointer;
  text-decoration: underline;
  padding: 4px;
}

.text-link:hover {
  color: #ffffff;
}

/* ===================================================================
   МОДАЛЬНЫЕ ОКНА
   =================================================================== */

.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.65);
  backdrop-filter: blur(4px);
  z-index: 999;
  display: none;
  align-items: center;
  justify-content: center;
  padding: 16px;
}

.modal-backdrop.open {
  display: flex;
}

.modal-card {
  background: #ffffff;
  border-radius: var(--radius-xl);
  max-width: 480px;
  width: 100%;
  padding: 28px 24px;
  text-align: center;
  box-shadow: var(--shadow-lg);
  animation: modalPop 0.25s ease-out;
  position: relative;
  max-height: 90vh;
  overflow-y: auto;
}

.modal-wide {
  max-width: 820px;
  text-align: left;
}

.modal-header-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
}

.close-x {
  background: transparent;
  border: none;
  font-size: 26px;
  line-height: 1;
  color: #6b7280;
  cursor: pointer;
}

.close-x:hover {
  color: #111827;
}

@keyframes modalPop {
  0% { transform: scale(0.9); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}

.modal-icon {
  font-size: 48px;
  margin-bottom: 12px;
}

.modal-title {
  font-size: 22px;
  font-weight: 800;
  margin-bottom: 8px;
  color: #111827;
}

.modal-desc {
  font-size: 14px;
  color: #4b5563;
  margin-bottom: 18px;
  line-height: 1.5;
}

.lead-summary {
  background: #f3f4f6;
  border-radius: var(--radius-md);
  padding: 12px;
  text-align: left;
  font-size: 13px;
  margin-bottom: 20px;
  color: #1f2937;
}

.leads-toolbar {
  display: flex;
  gap: 10px;
  margin-bottom: 14px;
}

.table-responsive {
  overflow-x: auto;
}

.leads-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 12px;
  text-align: left;
}

.leads-table th {
  background: #f3f4f6;
  padding: 10px;
  border-bottom: 2px solid #e5e7eb;
  font-weight: 700;
  color: #374151;
}

.leads-table td {
  padding: 9px 10px;
  border-bottom: 1px solid #e5e7eb;
}

.empty-table {
  text-align: center;
  color: #9ca3af;
  padding: 24px !important;
}

.code-box {
  background: #1f2937;
  color: #10b981;
  padding: 12px;
  border-radius: var(--radius-sm);
  font-size: 12px;
  overflow-x: auto;
  margin: 12px 0;
  font-family: Consolas, Monaco, monospace;
}

.instructions-content ol {
  padding-left: 20px;
  font-size: 13px;
  line-height: 1.6;
  color: #374151;
}

.instructions-content li {
  margin-bottom: 8px;
}

.gscript-input-group {
  margin-top: 14px;
  background: #f9fafb;
  padding: 14px;
  border-radius: var(--radius-md);
  border: 1px solid #e5e7eb;
}

.gscript-input-group input {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid #d1d5db;
  border-radius: var(--radius-sm);
  font-size: 13px;
  margin: 8px 0;
}

.mt-4 {
  margin-top: 16px;
}

</style>
</head>
<body class="theme-vkusvill" id="pageBody">

  <!-- ШАПКА САЙТА -->
  <header class="header">
    <div class="container header-container">
      <div class="logo-box">
        <div class="logo-icon" id="brandLogo">
          <!-- Логотип подставляется скриптом (SVG) -->
        </div>
        <div class="logo-text">
          <span class="brand-title" id="brandName">ВкусВилл</span>
          <span class="brand-badge" id="brandBadge">Официальный набор партнеров</span>
        </div>
      </div>
      <div class="header-phone">
        <span class="status-indicator"></span>
        <span id="calloutText">Набор открыт в вашем городе</span>
      </div>
    </div>
  </header>

  <!-- ГЛАВНЫЙ БАННЕР -->
  <section class="hero">
    <div class="container hero-container">
      <div class="hero-badge" id="heroBadge">🟢 Свежие вакансии с ежедневным доходом</div>
      <h1 class="hero-title" id="heroTitle">Работа во ВкусВилл: быстрый доход рядом с домом</h1>
      <p class="hero-subtitle" id="heroSubtitle">Выплаты без задержек, честные условия, свободный график и выбор удобного района</p>
      
      <div class="hero-highlights" id="heroHighlights">
        <div class="highlight-item">
          <span class="hl-icon">⚡</span>
          <span class="hl-text" id="hl1">Выплаты каждый день</span>
        </div>
        <div class="highlight-item">
          <span class="hl-icon">📍</span>
          <span class="hl-text" id="hl2">Рядом с вашим домом</span>
        </div>
        <div class="highlight-item">
          <span class="hl-icon">🕒</span>
          <span class="hl-text" id="hl3">Смены от 4 до 12 часов</span>
        </div>
        <div class="highlight-item">
          <span class="hl-icon">🛡️</span>
          <span class="hl-text" id="hl4">Без опыта — обучаем за 1 день</span>
        </div>
      </div>

      <div class="hero-cta-row">
        <a href="#vacancies" class="btn btn-primary" id="heroCtaBtn">Выбрать вакансию</a>
        <a href="#calc" class="btn btn-secondary">Рассчитать доход</a>
      </div>
    </div>
  </section>

  <!-- КАРТОЧКИ ВАКАНСИЙ (3 ПРОФЕССИИ) -->
  <section class="section" id="vacancies">
    <div class="container">
      <div class="section-head">
        <h2 class="section-title">Выберите подходящую профессию</h2>
        <p class="section-desc">Нажмите «Выбрать», чтобы рассчитать заработок и подать заявку</p>
      </div>

      <div class="cards-grid" id="vacancyCards">
        <!-- Карточки генерируются динамически под выбранный бренд -->
      </div>
    </div>
  </section>

  <!-- КАЛЬКУЛЯТОР ЗАРАБОТКА С ПОЛЗУНКАМИ ДО 12 ЧАСОВ -->
  <section class="section calc-section" id="calc">
    <div class="container">
      <div class="calc-wrapper">
        <div class="calc-head">
          <span class="calc-tag">🧮 Интерактивный калькулятор</span>
          <h2 class="calc-title">Сколько вы будете зарабатывать?</h2>
          <p class="calc-desc">Двигайте ползунки, чтобы настроить количество часов и рабочих дней</p>
        </div>

        <div class="calc-body">
          <div class="calc-controls">
            <!-- Выбор роли для калькулятора -->
            <div class="control-group">
              <label class="control-label">Профессия:</label>
              <div class="role-selector" id="roleSelector">
                <!-- Кнопки ролей генерируются скриптом -->
              </div>
            </div>

            <!-- Ползунок часов (до 12 часов) -->
            <div class="control-group">
              <div class="control-header">
                <label for="hoursSlider" class="control-label">Часов в смену:</label>
                <span class="slider-val" id="hoursVal">8 часов</span>
              </div>
              <input type="range" id="hoursSlider" min="4" max="12" step="1" value="8" class="range-slider">
              <div class="range-labels">
                <span>4 ч (подработка)</span>
                <span>8 ч (стандарт)</span>
                <span>12 ч (макс)</span>
              </div>
            </div>

            <!-- Ползунок дней в неделю -->
            <div class="control-group">
              <div class="control-header">
                <label for="daysSlider" class="control-label">Дней в неделю:</label>
                <span class="slider-val" id="daysVal">5 дней</span>
              </div>
              <input type="range" id="daysSlider" min="1" max="7" step="1" value="5" class="range-slider">
              <div class="range-labels">
                <span>1 день</span>
                <span>3 дня</span>
                <span>5 дней</span>
                <span>7 дней</span>
              </div>
            </div>
          </div>

          <!-- Результат расчета дохода -->
          <div class="calc-result-box">
            <div class="result-badge">Прогноз дохода</div>
            <div class="result-row">
              <span class="result-sublabel">За одну смену:</span>
              <div class="result-price" id="calcShiftTotal">0 ₽</div>
            </div>
            <div class="result-row primary-result">
              <span class="result-sublabel">В месяц (~4 недели):</span>
              <div class="result-price-month" id="calcMonthTotal">0 ₽</div>
            </div>
            <div class="result-details">
              <div class="res-item">
                <span class="res-muted">Ориентир:</span>
                <strong id="calcRateInfo">0 ₽ / час</strong>
              </div>
              <div class="res-item">
                <span class="res-muted">Часов в месяц:</span>
                <strong id="calcHoursMonth">160 ч</strong>
              </div>
            </div>
            <a href="#apply-form" class="btn btn-primary btn-block" onclick="applyCalcToForm()">
              Перейти к анкете
            </a>
            <p class="calc-note">* Примерный расчёт: суммы за 12 часов пересчитаны пропорционально выбранному времени, месяц — 4 недели. Фактический доход может отличаться.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- БЫСТРАЯ АНКЕТА (ОБРАТНАЯ СВЯЗЬ) -->
  <section class="section form-section" id="apply-form">
    <div class="container">
      <div class="form-card">
        <div class="form-header">
          <div class="form-icon">📝</div>
          <h2 class="form-title" id="formHeaderTitle">Быстрая анкета соискателя</h2>
          <p class="form-subtitle">Черновик: форма пока не подключена. Пожалуйста, не вводите личные данные.</p>
        </div>

        <form id="jobForm" novalidate>
          <fieldset disabled style="border:0;padding:0;margin:0">
          <div class="form-row">
            <div class="form-field">
              <label for="applicantName">Ваше имя <span class="req">*</span></label>
              <input type="text" id="applicantName" name="name" placeholder="Например: Иван" required autocomplete="name">
              <span class="field-error" id="nameError"></span>
            </div>

            <div class="form-field">
              <label for="applicantPhone">Номер телефона <span class="req">*</span></label>
              <input type="tel" id="applicantPhone" name="phone" placeholder="+7 (___) ___-__-__" required autocomplete="tel">
              <span class="field-error" id="phoneError"></span>
            </div>
          </div>

          <div class="form-row">
            <div class="form-field">
              <label for="applicantVacancy">Вакансия <span class="req">*</span></label>
              <select id="applicantVacancy" name="vacancy" required>
                <!-- Опции заполняются динамически -->
              </select>
            </div>

            <div class="form-field">
              <label for="applicantExp">Стаж / Опыт работы</label>
              <select id="applicantExp" name="experience">
                <option value="Без опыта">Без опыта (научим с нуля)</option>
                <option value="До 1 года">До 1 года</option>
                <option value="1–3 года">От 1 до 3 лет</option>
                <option value="Более 3 лет">Более 3 лет</option>
              </select>
            </div>
          </div>

          <div class="form-field">
            <label for="applicantLastJob">Где работали последним местом (или напишите «нет опыта»)</label>
            <input type="text" id="applicantLastJob" name="lastJob" placeholder="Компания, сфера или должность (необязательно)">
          </div>

          <div class="form-field">
            <label for="applicantCity">Город / Район проживания</label>
            <input type="text" id="applicantCity" name="city" placeholder="Например: Москва, м. Сокол">
          </div>

          <div class="form-agreement">
            <label class="checkbox-container">
              <input type="checkbox" id="agreeData" checked required>
              <span class="checkmark"></span>
              <span class="agreement-text">
                Я согласен на обработку персональных данных и обратный звонок по вакансии. Данные передаются конфиденциально.
              </span>
            </label>
          </div>

          <button type="submit" class="btn btn-primary btn-submit" id="submitBtn">
            <span class="btn-text" id="submitBtnText">Получить работу</span>
            <span class="btn-spinner" style="display:none;">⏳</span>
          </button>
          </fieldset>
        </form>

        <div class="form-footer-guarantee">
          <span>🔒 Конфиденциально</span>
          <span>⚠️ Приём заявок пока не подключён</span>
          <span>🆓 Бесплатное трудоустройство</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ПРЕИМУЩЕСТВА КОМПАНИИ -->
  <section class="section perks-section">
    <div class="container">
      <div class="section-head">
        <h2 class="section-title" id="perksTitle">Почему работать у нас выгодно</h2>
        <p class="section-desc">Удобные условия для каждого партнера и сотрудника</p>
      </div>

      <div class="perks-grid" id="perksGrid">
        <!-- Генерируется под бренд -->
      </div>
    </div>
  </section>

  <!-- ФУТЕР -->
  <footer class="footer">
    <div class="container footer-container">
      <div class="footer-brand">
        <span class="footer-logo-text" id="footerBrand">ВкусВилл Работа</span>
        <p class="footer-copy">Сервис содействия быстрому трудоустройству в сфере доставки и ритейла. Не является публичной офертой.</p>
      </div>

    </div>
  </footer>

  <script>
/* ===================================================================
   СКРИПТ ЛЕНДИНГА: ВКУСВИЛЛ И ПЯТЁРОЧКА
   Интерактивный калькулятор дохода (до 12 часов), выбор вакансий,
   валидация формы, маска телефона, экспорт лидов в Google Таблицы и CSV
   =================================================================== */

// ДАННЫЕ ДВУХ БРЕНДОВ
const BRANDS_DATA = {
  vkusvill: {
    id: 'vkusvill',
    name: 'ВкусВилл',
    title: 'ВкусВилл Работа',
    badge: 'Официальный набор партнеров',
    themeClass: 'theme-vkusvill',
    callout: 'Набор открыт в вашем районе',
    hero: {
      badge: '🟢 Свежие вакансии с ежедневным доходом',
      title: 'Работа во ВкусВилл: быстрый доход рядом с домом',
      subtitle: 'Выплаты без задержек каждый день, честные условия, свободный график от 4 до 12 часов и выбор удобного магазина у дома',
      highlights: [
        { icon: '⚡', text: 'Выплаты каждый день' },
        { icon: '📍', text: 'Рядом с вашим домом' },
        { icon: '🕒', text: 'Смены от 4 до 12 часов' },
        { icon: '🍏', text: 'Скидка 20% на продукты' }
      ]
    },
    logoSvg: `
      <svg viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect width="100" height="100" rx="22" fill="#006643"/>
        <!-- Стилизованный лист и ягода ВкусВилл -->
        <path d="M50 20C50 20 72 26 72 48C72 65 58 78 50 82C42 78 28 65 28 48C28 26 50 20 50 20Z" fill="#12B886"/>
        <path d="M50 22C50 22 40 45 50 78" stroke="#ffffff" stroke-width="4" stroke-linecap="round"/>
        <circle cx="50" cy="46" r="10" fill="#ffffff"/>
        <circle cx="50" cy="46" r="6" fill="#006643"/>
      </svg>
    `,
    vacancies: [
      {
        id: 'picker',
        name: 'Сборщик заказов',
        icon: '🎒',
        badge: 'В дарксторе у дома',
        min12: 5000, max12: 6000,
        dayRateText: '5 000–6 000 ₽ / 12 часов',
        hoursNote: '⏱️ Смены от 4 до 12 часов',
        desc: 'Комплектация и сборка заказов по удобному приложению в тёплом магазине или дарксторе. Без тяжестей и без поездок.',
        bullets: [
          'Обучение за 1 день с наставником',
          'Тёплое помещение, дружная команда',
          'Скидка 20% на весь ассортимент ВкусВилл'
        ]
      },
      {
        id: 'bike',
        name: 'Курьер на велосипеде',
        icon: '🚲',
        badge: 'Быстрый старт',
        min12: 7000, max12: 13000,
        dayRateText: '7 000–13 000 ₽ / 12 часов',
        hoursNote: '⏱️ Смены от 4 до 12 часов',
        desc: 'Доставка свежих продуктов покупателям в радиусе 1.5–3 км от магазина. Выдаем велосипед или работайте на своём.',
        bullets: [
          'Компактный радиус доставки у дома',
          'Компенсация обслуживания велосипеда',
          'Выплаты на любую карту каждый день'
        ]
      },
      {
        id: 'car',
        name: 'Авто-курьер',
        icon: '🚗',
        badge: 'До 13 000 ₽ / 12 часов',
        min12: 10000, max12: 13000,
        dayRateText: '10 000–13 000 ₽ / 12 часов',
        hoursNote: '⏱️ Свободный график',
        desc: 'Доставка заказов на личном авто. Оплата за каждый заказ + доплата за километраж и тяжелые пакеты.',
        bullets: [
          'Компенсация ГСМ и амортизации',
          'Свободное расписание от 4 до 12 ч',
          'Примерный доход зависит от графика и количества заказов'
        ]
      }
    ],
    perks: [
      {
        icon: '💳',
        title: 'Ежедневные выплаты',
        desc: 'Деньги поступают на любую банковскую карту каждый день без задержек и скрытых комиссий.'
      },
      {
        icon: '🏥',
        title: 'Медкнижка бесплатно',
        desc: 'Помогаем официально оформить медицинскую книжку и компенсируем 100% её стоимости.'
      },
      {
        icon: '🥗',
        title: 'Скидка 20% на продукты',
        desc: 'Каждый сотрудник и партнер получает корпоративную скидку на полезную еду ВкусВилл.'
      },
      {
        icon: '🏡',
        title: 'Работа у дома',
        desc: 'Подберем магазин или склад в 10–15 минутах от вашего дома, чтобы не тратить время на дорогу.'
      }
    ]
  }
};

// ТЕКУЩЕЕ СОСТОЯНИЕ
let currentBrand = 'vkusvill';
let currentRoleId = 'picker';
let currentHours = 8;
let currentDays = 5;

// ИНИЦИАЛИЗАЦИЯ ПРИ ЗАГРУЗКЕ
document.addEventListener('DOMContentLoaded', function () {
  // Навешиваем слушатели на ползунки
  const hoursSlider = document.getElementById('hoursSlider');
  const daysSlider = document.getElementById('daysSlider');

  if (hoursSlider) {
    hoursSlider.addEventListener('input', function (e) {
      currentHours = parseInt(e.target.value, 10);
      document.getElementById('hoursVal').textContent = currentHours + ' ' + getHoursWord(currentHours);
      calculateIncome();
    });
  }

  if (daysSlider) {
    daysSlider.addEventListener('input', function (e) {
      currentDays = parseInt(e.target.value, 10);
      document.getElementById('daysVal').textContent = currentDays + ' ' + getDaysWord(currentDays);
      calculateIncome();
    });
  }

  // Маска для телефона (+7 (999) 123-45-67)
  const phoneInput = document.getElementById('applicantPhone');
  if (phoneInput) {
    initPhoneMask(phoneInput);
  }

  // Обработка отправки формы
  const form = document.getElementById('jobForm');
  if (form) {
    form.addEventListener('submit', handleFormSubmit);
  }

  // Применяем выбранный бренд
  applyBrand(currentBrand);
});

// ПРИМЕНЕНИЕ СТИЛЕЙ И КОНТЕНТА БРЕНДА
function applyBrand(brandKey) {
  const brand = BRANDS_DATA[brandKey];
  const body = document.getElementById('pageBody');

  // Переключаем классы темы на body
  body.className = brand.themeClass;

  // Кнопки тумблера

  // Шапка
  document.getElementById('brandLogo').innerHTML = brand.logoSvg;
  document.getElementById('brandName').textContent = brand.name;
  document.getElementById('brandBadge').textContent = brand.badge;
  document.getElementById('calloutText').textContent = brand.callout;
  document.getElementById('footerBrand').textContent = brand.title;

  // Hero
  document.getElementById('heroBadge').textContent = brand.hero.badge;
  document.getElementById('heroTitle').textContent = brand.hero.title;
  document.getElementById('heroSubtitle').textContent = brand.hero.subtitle;

  // Hero Highlights
  brand.hero.highlights.forEach((hl, idx) => {
    const el = document.getElementById('hl' + (idx + 1));
    if (el) el.textContent = hl.text;
  });

  // Кнопка в Hero
  document.getElementById('heroCtaBtn').textContent = 'Выбрать вакансию в ' + brand.name;
  document.getElementById('formHeaderTitle').textContent = 'Анкета для работы в ' + brand.name;
  document.getElementById('submitBtnText').textContent = 'Приём заявок пока не подключён';
  document.getElementById('perksTitle').textContent = 'Почему работать в ' + brand.name + ' выгодно';

  // Рендер карточек вакансий
  renderVacancyCards(brand.vacancies);

  // Рендер селектора ролей в калькуляторе
  renderRoleSelector(brand.vacancies);

  // Обновление селекта в форме
  updateFormVacancySelect(brand.vacancies);

  // Рендер преимуществ
  renderPerks(brand.perks);

  // Пересчитываем доход
  calculateIncome();
}

// РЕНДЕР КАРТОЧЕК ВАКАНСИЙ
function renderVacancyCards(vacancies) {
  const container = document.getElementById('vacancyCards');
  if (!container) return;

  container.innerHTML = vacancies.map(vac => `
    <div class="job-card" id="card-${vac.id}">
      <div class="card-top">
        <span class="card-icon">${vac.icon}</span>
        <span class="card-badge">${vac.badge}</span>
      </div>
      <h3 class="card-title">${vac.name}</h3>
      <div class="card-income-box">
        <span class="card-income-label">Примерный доход за 12 часов:</span>
        <div class="card-income-val">${vac.dayRateText}</div>
        <div class="card-rate-sub">${vac.hoursNote}</div>
      </div>
      <p class="card-desc">${vac.desc}</p>
      <ul class="card-bullets">
        ${vac.bullets.map(b => `<li>${b}</li>`).join('')}
      </ul>
      <button type="button" class="btn-card-select" onclick="selectRole('${vac.id}')">
        Выбрать и рассчитать
      </button>
    </div>
  `).join('');
}

// РЕНДЕР РОЛЕЙ В КАЛЬКУЛЯТОРЕ
function renderRoleSelector(vacancies) {
  const container = document.getElementById('roleSelector');
  if (!container) return;

  container.innerHTML = vacancies.map(vac => `
    <button type="button" 
      class="role-opt-btn ${vac.id === currentRoleId ? 'active' : ''}" 
      id="roleBtn-${vac.id}" 
      onclick="setCalcRole('${vac.id}')">
      <span class="role-icon">${vac.icon}</span>
      <span>${vac.name}</span>
    </button>
  `).join('');
}

// ОБНОВЛЕНИЕ SELECT В ФОРМЕ
function updateFormVacancySelect(vacancies) {
  const select = document.getElementById('applicantVacancy');
  if (!select) return;

  select.innerHTML = vacancies.map(vac => `
    <option value="${vac.name}" ${vac.id === currentRoleId ? 'selected' : ''}>
      ${vac.icon} ${vac.name} (${vac.dayRateText})
    </option>
  `).join('');
}

// РЕНДЕР ПРЕИМУЩЕСТВ
function renderPerks(perks) {
  const container = document.getElementById('perksGrid');
  if (!container) return;

  container.innerHTML = perks.map(p => `
    <div class="perk-card">
      <div class="perk-icon">${p.icon}</div>
      <h4 class="perk-title">${p.title}</h4>
      <p class="perk-desc">${p.desc}</p>
    </div>
  `).join('');
}

// ВЫБОР РОЛИ ИЗ КАРТОЧКИ (ПЕРЕХОД К КАЛЬКУЛЯТОРУ И ФОРМЕ)
function selectRole(roleId) {
  setCalcRole(roleId);

  // Скроллим плавно к калькулятору
  const calcEl = document.getElementById('calc');
  if (calcEl) {
    calcEl.scrollIntoView({ behavior: 'smooth' });
  }
}

// УСТАНОВКА РОЛИ В КАЛЬКУЛЯТОРЕ
function setCalcRole(roleId) {
  currentRoleId = roleId;

  // Обновляем активную кнопку
  const brand = BRANDS_DATA[currentBrand];
  brand.vacancies.forEach(v => {
    const btn = document.getElementById('roleBtn-' + v.id);
    if (btn) btn.classList.toggle('active', v.id === roleId);
  });

  // Синхронизируем форму
  const select = document.getElementById('applicantVacancy');
  if (select) {
    const selectedVac = brand.vacancies.find(v => v.id === roleId);
    if (selectedVac) {
      select.value = selectedVac.name;
    }
  }

  calculateIncome();
}

// РАСЧЕТ ДОХОДА
function calculateIncome() {
  const brand = BRANDS_DATA[currentBrand];
  const vacancy = brand.vacancies.find(v => v.id === currentRoleId) || brand.vacancies[0];

  // Прогноз пропорционально указанному диапазону за 12 часов; месяц = 4 недели.
  const shiftsPerMonth = currentDays * 4;
  const low = vacancy.min12 * currentHours / 12;
  const high = vacancy.max12 * currentHours / 12;
  const range = (a, b) => formatMoney(Math.round(a)) + ' – ' + formatMoney(Math.round(b));
  document.getElementById('calcShiftTotal').textContent = range(low, high);
  document.getElementById('calcMonthTotal').textContent = range(low * shiftsPerMonth, high * shiftsPerMonth);
  document.getElementById('calcRateInfo').textContent = range(vacancy.min12, vacancy.max12) + ' / 12 ч';
  document.getElementById('calcHoursMonth').textContent = (currentHours * shiftsPerMonth) + ' ч / мес';
}

function formatMoney(num) {
  return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ' ') + ' ₽';
}

function getHoursWord(h) {
  if (h === 1) return 'час';
  if (h >= 2 && h <= 4) return 'часа';
  return 'часов';
}

function getDaysWord(d) {
  if (d === 1) return 'день';
  if (d >= 2 && d <= 4) return 'дня';
  return 'дней';
}

// ПЕРЕНОС ДАННЫХ КАЛЬКУЛЯТОРА В ФОРМУ
function applyCalcToForm() {
  const formEl = document.getElementById('apply-form');
  if (formEl) {
    formEl.scrollIntoView({ behavior: 'smooth' });
  }

  // Фокусируемся на имени
  setTimeout(() => {
    const nameInput = document.getElementById('applicantName');
    if (nameInput) nameInput.focus();
  }, 400);
}

// МАСКА ТЕЛЕФОНА
function initPhoneMask(input) {
  input.addEventListener('input', function (e) {
    let x = e.target.value.replace(/\D/g, '');
    if (x.startsWith('7') || x.startsWith('8')) {
      x = x.substring(1);
    }
    x = x.substring(0, 10);

    let formatted = '+7 ';
    if (x.length > 0) formatted += '(' + x.substring(0, 3);
    if (x.length >= 3) formatted += ') ' + x.substring(3, 6);
    if (x.length >= 6) formatted += '-' + x.substring(6, 8);
    if (x.length >= 8) formatted += '-' + x.substring(8, 10);

    e.target.value = x.length > 0 ? formatted : '';
  });

  input.addEventListener('keydown', function (e) {
    if (e.key === 'Backspace' && e.target.value === '+7 ') {
      e.target.value = '';
    }
  });
}

// Форма отключена до подключения проверенного сервиса приёма заявок.
function handleFormSubmit(e) {
  e.preventDefault();
  alert('Приём заявок пока не подключён.');
}

</script>
</body>
</html>
