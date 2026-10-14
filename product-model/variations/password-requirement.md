---
{
  "kind": "configuration",
  "of": "business-rule",
  "settings": [
    {
      "entity": "instance-settings",
      "fact": "Password requirement"
    }
  ],
  "takesEffect": "Whenever a password is set: at registration, on a password change and on a reset. Passwords already set are not checked again.",
  "stability": "Changing the requirement leaves existing passwords valid until their holders change them.",
  "alternatives": [
    {
      "id": "password-length-only",
      "selectedWhen": "Password requirement is “Minimum password length”, the default."
    },
    {
      "id": "password-with-mixed-case",
      "selectedWhen": "Password requirement asks for upper- and lower-case letters."
    },
    {
      "id": "password-with-mixed-case-and-digit",
      "selectedWhen": "Password requirement asks for upper- and lower-case letters and a digit."
    },
    {
      "id": "password-with-mixed-case-digit-and-symbol",
      "selectedWhen": "Password requirement asks for upper- and lower-case letters, a digit and a special character."
    }
  ]
}
---

# Password requirement

Each instance chooses how strong local passwords must be; all four policies are supported, each on top of the instance's minimum length.
