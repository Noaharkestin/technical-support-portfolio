# KB-0002 – Recovering a WordPress Site After a Faulty Plugin Update

## Overview

This knowledge base article demonstrates how to diagnose and recover a WordPress website that displays a **"There has been a critical error on this website"** message after a plugin update introduced a PHP syntax error.

---

## Environment

- LocalWP
- WordPress (Latest Version)
- Twenty Twenty-Five Theme
- Custom Test Plugin (Noah Test Plugin)
- PHP (LocalWP Preferred Environment)

---

## Scenario

A plugin update introduced a PHP syntax error, causing the website to fail with a critical error. The objective was to restore the website, identify the faulty plugin, correct the code, and verify normal operation.

---

## Symptoms

- Website displayed:
  > There has been a critical error on this website.
- WordPress frontend failed to load.
- Plugin had recently been modified.

---

## Root Cause

A PHP syntax error was introduced into the plugin by removing the semicolon after an `echo` statement.

Broken code:

```php
echo "<p style='text-align:center;'>Noah Test Plugin Active</p>"
```

Correct code:

```php
echo "<p style='text-align:center;'>Noah Test Plugin Active</p>";
```

---

## Investigation

1. Confirmed the issue occurred immediately after modifying the plugin.
2. Identified the custom plugin as the most recent change.
3. Determined that the plugin was preventing WordPress from loading correctly.
4. Disabled the plugin by renaming its folder in:

```
wp-content/plugins/
```

5. Confirmed the website loaded successfully after the plugin was disabled.

---

## Resolution

1. Renamed the plugin folder to temporarily disable it.
2. Restored the missing semicolon in the plugin code.
3. Renamed the plugin folder back to its original name.
4. Reactivated the plugin.
5. Confirmed the website loaded successfully.

---

## Verification

- Homepage loaded successfully.
- WordPress Admin was accessible.
- Plugin activated without causing a critical error.
- Website functionality returned to normal.

---

## Lessons Learned

- Always identify the most recent change when troubleshooting.
- A single PHP syntax error inside a plugin can bring down an entire WordPress site.
- Renaming a plugin folder is an effective recovery technique when the WordPress dashboard is unavailable.
- Test plugin updates in a development environment before deploying them to production.

---

## Skills Demonstrated

- WordPress Troubleshooting
- Plugin Conflict Diagnosis
- PHP Error Analysis
- Root Cause Analysis
- Website Recovery
- Technical Documentation
- Customer Support
