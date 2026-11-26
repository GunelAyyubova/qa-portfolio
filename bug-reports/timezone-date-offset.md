# Bug Report: Date of Birth Shifts One Day Backward After Saving (Timezone / UTC Offset)

**Bug ID:** BUG-001  
**Severity:** Minor / Medium  
**Priority:** Medium  
**Environment:** Web Application – User Profile Page (Desktop Browser)  
**Status:** Reported  

## Summary
When entering and saving a Date of Birth on the user profile page, the displayed date shifts one day backward (for example, `16-05-2001` is displayed as `15-05-2001` after saving).

## Preconditions
- User is logged into the portal.
- User navigates to the **Profile / Personal Information** page.

## Steps to Reproduce
1. Open the **Personal Information** edit form.
2. Enter a valid date in the **Date of Birth** field (e.g., `16-05-2001`).
3. Click the **Save** button.
4. Check the saved Date of Birth displayed on the profile page.

## Expected Result
The Date of Birth should be saved and displayed exactly as entered (`16-05-2001`).

## Actual Result
The Date of Birth is displayed one day earlier (`15-05-2001`).

## Possible Root Cause
Likely caused by timezone/UTC conversion handling (e.g., saving local midnight `+04:00` as UTC or converting a UTC date string back to local timezone without stripping the time component).
