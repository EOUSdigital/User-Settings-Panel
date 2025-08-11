# Step 6: Project Integration — "User Settings Panel"

## 🖼️ Scenario:
You are developing a small web UI component called **User Settings Panel**. The data structure you receive from the backend is:

```javascript
const userSettings = {
  name: 'Alice',
  theme: 'light',
  emailNotifications: true,
  roles: ['admin', 'editor'],
};
```

---

## ✅ Objective:
Write a function `renderUserSettings(settings)` that logs the user's configuration using the following rules:

### 📌 Requirements:
1. Use a `for...in` loop to iterate over all the **keys** in `settings`.
2. If a property's value is an array (like `roles`), use a **nested `for...of` loop** to list each role individually.
3. Use `.hasOwnProperty()` to avoid inherited properties.
4. Output should look like this:
```
name: Alice
theme: light
emailNotifications: true
roles:
  - admin
  - editor
```

---

## 🧮 Solution:
```javascript
function renderUserSettings(settings) {
  for (const key in settings) {
    if (settings.hasOwnProperty(key)) {
      const value = settings[key];

      if (Array.isArray(value)) {
        console.log(`${key}:`);
        for (const item of value) {
          console.log(`  - ${item}`);
        }
      } else {
        console.log(`${key}: ${value}`);
      }
    }
  }
}

renderUserSettings(userSettings);
```

---

## 📝 Expected Output:
```
name: Alice
theme: light
emailNotifications: true
roles:
  - admin
  - editor
```
