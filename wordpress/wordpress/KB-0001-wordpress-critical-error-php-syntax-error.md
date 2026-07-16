# KB-0001 – WordPress Critical Error Caused by a PHP Syntax Error

## Overview

This knowledge base article explains how to diagnose and resolve a WordPress "There has been a critical error on this website" message caused by a PHP syntax error in the active theme's `functions.php` file.

---

## Environment

- LocalWP
- WordPress (latest version)
- Twenty Twenty-Five theme
- PHP (LocalWP Preferred Environment)

---

## Symptoms

- Website displayed:
  > There has been a critical error on this website.
- WordPress frontend failed to load.
- The PHP error identified a syntax issue in `functions.php`.

---

## Error Message

```
Parse error: syntax error, unexpected token "}", expecting "," or ";"
```

---

## Root Cause

A missing semicolon (`;`) after an `echo` statement in `functions.php` caused PHP to stop parsing the file, resulting in a fatal error that prevented WordPress from loading.

---

## Investigation

1. Read the PHP error message.
2. Identified the affected file:
   `wp-content/themes/twentytwentyfive/functions.php`
3. Reviewed the code near the reported line number.
4. Found a missing semicolon after an `echo` statement.

---

## Resolution

1. Added the missing semicolon.
2. Saved the file.
3. Refreshed the website.
4. Confirmed that both the homepage and WordPress admin dashboard loaded successfully.

---

## Verification

- Homepage loaded correctly.
- WordPress admin was accessible.
- The custom footer text displayed as expected.

---

## Lessons Learned

- Always review PHP syntax carefully before saving changes.
- Read the full PHP error message—it usually points directly to the file and approximate location of the issue.
- Create a backup before editing theme files.
- Test code changes in a local development environment before applying them to production.

---

## Skills Demonstrated

- WordPress Troubleshooting
- PHP Error Diagnosis
- Root Cause Analysis
- Technical Documentation
- Website Recovery
- Technical Support
