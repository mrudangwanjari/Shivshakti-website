# Formspree Integration Guide

## Overview

The registration form on the Shivshakti Gurukulam website is integrated with Formspree to handle form submissions.

## Formspree Endpoint

- **URL**: `https://formspree.io/f/mgonldog`
- **Method**: POST
- **Encoding**: multipart/form-data (supports file uploads)

## Form Fields

The registration form collects the following information:

1. **Full Name** (`fullName`) - Required text field
2. **Age** (`age`) - Required number field (6-80)
3. **Mobile Number** (`phone`) - Required tel field
4. **Email** (`email`) - Required email field
5. **Gender** (`gender`) - Required select field (Male/Female/Other)
6. **Interested Program** (`program`) - Required select field
   - Talwarbaazi
   - Dandpatta
   - Lathi-Kathi
   - Self Defence
   - Yoga & Akhada
   - Trekking
   - All Programs
7. **Address** (`address`) - Required textarea
8. **Photo** (`photo`) - Optional file upload (images only)

## Features

### Form Validation
- All fields except photo are required
- Age must be between 6 and 80
- Email format validation
- Phone number format validation

### User Feedback
- Loading state during submission (button shows "⏳ Submitting...")
- Success message: "✅ Registration successful! We will contact you soon."
- Error message: "❌ Something went wrong. Please try again or contact us directly."
- Form automatically resets after successful submission

### File Upload
- Supports image uploads (JPG, PNG)
- Files are sent to Formspree along with form data
- Custom upload UI with click-to-upload functionality

## How It Works

1. User fills out the registration form
2. On submit, JavaScript intercepts the form submission
3. Form data is sent to Formspree via AJAX (fetch API)
4. Formspree processes the submission and sends email notification
5. User receives immediate feedback (success/error message)
6. Form resets on successful submission

## Receiving Submissions

Submissions will be sent to the email address configured in your Formspree account for the form ID `mgonldog`.

## Testing

To test the form:
1. Open `frontend/index.html` in a browser
2. Navigate to the "Join" section
3. Fill out all required fields
4. Optionally upload a photo
5. Click "⚔ Join Shivshakti Gurukulam"
6. Check for success/error message
7. Verify email receipt in your Formspree dashboard

## Customization

To change the Formspree endpoint, update the `action` attribute in the form tag:

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

## Notes

- Formspree free tier has submission limits (check your plan)
- File uploads count toward your storage quota
- Spam protection is built into Formspree
- No backend server required - Formspree handles everything
