---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "account",
      "fact": "Two-factor authentication"
    },
    {
      "entity": "instance-settings",
      "fact": "Enforce two-factor authentication"
    }
  ],
  "takesEffect": "At each sign-in, from the person's own setting and the instance's enforcement for their role.",
  "stability": "A session already signed in is unaffected by a later change of either setting.",
  "alternatives": [
    {
      "id": "sign-in-with-password",
      "selectedWhen": "The account does not use two-factor authentication and the instance does not require it of the person: Enforce two-factor authentication is off, or covers Sysadmins or Admins and the person is neither."
    },
    {
      "id": "sign-in-with-password-and-code",
      "selectedWhen": "The account uses two-factor authentication, or the instance requires it of everyone, of Sysadmins and the person is one, or of Admins and the person is an Admin of a team."
    }
  ]
}
---

# Two-factor sign-in

Whether signing in asks for a code from an authenticator app depends on the person's own choice and on what the instance requires; both ways of signing in are supported.
