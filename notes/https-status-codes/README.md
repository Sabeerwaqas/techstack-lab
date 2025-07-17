# 🌐 Common HTTP Status Codes – Beginner-Friendly Guide

This guide lists the most frequently used HTTP status codes every developer should know. Whether you're building APIs, web apps, or handling routing, understanding these codes will help you manage user behavior, debugging, and SEO.

---

## ✅ 2xx – Success

### `200 OK`
> The request was successful.

Use it when everything works perfectly and the server sends back the requested data.

---

### `201 Created`
> A new resource has been successfully created.

Use it after `POST` requests that create something (like a new user or post).

---

## ⚠️ 3xx – Redirects

### `301 Moved Permanently`
> The URL has changed **forever**.

- Browsers and search engines remember the new location.
- Great for SEO when you've restructured your site.

💡 Use when:  
You move `/blog` to `/articles` and want Google to rank the new URL.

---

### `302 Found (Temporary Redirect)`
> The URL has changed **temporarily**.

- Browsers follow the redirect but **don't remember** it.
- Search engines keep showing the **original URL**.

💡 Use when:  
You're doing A/B testing or short-term maintenance.

---

### `308 Permanent Redirect`
> Like `301`, but it preserves the original request method (e.g., `POST` stays `POST`).

💡 Use when:  
You want a permanent redirect **and** need to keep the method (especially important in APIs).

---

## 🚫 4xx – Client Errors

### `400 Bad Request`
> The request is malformed or invalid.

💡 Use when:  
The user forgot a required field or sent bad data.

---

### `401 Unauthorized`
> User is not logged in or authentication failed.

💡 Use when:  
You're protecting a route (like `/dashboard`) and the user isn’t logged in.

---

### `403 Forbidden`
> The user is logged in but doesn’t have permission.

💡 Use when:  
A logged-in user tries to access an admin-only page.

---

### `404 Not Found`
> The server can’t find the requested page.

💡 Use when:  
The user visits a non-existent URL like `/nope`.

---

### `410 Gone`
> The page is **intentionally removed** and won’t come back.

💡 Use when:  
You’ve permanently deleted a product or article and want search engines to remove it from results.

✅ Better for SEO than 404 when you **know** a page is gone forever.

---

### `413 Payload Too Large`
> The file or request is too big for the server to handle.

💡 Use when:  
A user tries to upload a huge file (e.g., over your 5MB limit).

---

## 💥 5xx – Server Errors

### `500 Internal Server Error`
> Something went wrong on the server.

💡 Use when:  
Your code crashed, a database failed, or you want to signal a generic error.

---

## 📌 Summary Table

| Code | Meaning                | When to Use                                         |
|------|------------------------|-----------------------------------------------------|
| 200  | OK                     | Everything worked fine                              |
| 201  | Created                | Resource successfully created                       |
| 301  | Moved Permanently      | Permanent redirect (good for SEO)                  |
| 302  | Found (Temporary)      | Temporary redirect                                  |
| 308  | Permanent Redirect     | Like 301 but keeps POST/PUT methods                |
| 400  | Bad Request            | User sent invalid data                              |
| 401  | Unauthorized           | User is not authenticated                          |
| 403  | Forbidden              | User is authenticated but not allowed              |
| 404  | Not Found              | URL doesn't exist                                   |
| 410  | Gone                   | Page was deleted on purpose                        |
| 413  | Payload Too Large      | User sent too much data                             |
| 500  | Internal Server Error  | Something broke on the server                       |

---

## 🙌 Why This Matters

- Proper HTTP codes make your **API more readable**.
- Search engines rely on these for **SEO indexing**.
- Users get the **right message** when something goes wrong.
- Clean routing improves **performance and debugging**.

---

### 💡 Pro Tip:
Start using these codes in your API and route responses to build better, smarter apps. Even simple projects benefit from proper status handling!

---

> Feel free to fork, clone, or share this guide in your own documentation or project repos.

