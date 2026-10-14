---
{
  "scope": "The eLabFTW web application and REST API v2: entries, templates, statuses and categories, permissions, timestamping and signatures, scheduler, inventory, compounds, procurement, import and export, team and instance administration, local authentication with two-factor sign-in, and audit logging.",
  "method": "Static inspection of PHP, Twig, TypeScript, SQL schema and documentation at the pinned commit; nothing was executed.",
  "covered": [
    {
      "description": "Entry, template, status and category models with their permission checks",
      "paths": [
        "src/Models/AbstractEntity.php",
        "src/Models/AbstractConcreteEntity.php",
        "src/Models/AbstractTemplateEntity.php",
        "src/Models/Experiments.php",
        "src/Models/Items.php",
        "src/Models/Templates.php",
        "src/Models/ItemsTypes.php",
        "src/Models/AbstractStatus.php",
        "src/Models/AbstractCategory.php",
        "src/Models/ExperimentsStatus.php",
        "src/Models/ItemsStatus.php",
        "src/Models/ExperimentsCategories.php",
        "src/Models/ResourcesCategories.php",
        "src/Elabftw/Permissions.php",
        "src/Elabftw/AccessPermissions.php",
        "src/Enums/BasePermissions.php",
        "src/Enums/State.php"
      ]
    },
    {
      "description": "Entry sub-records: steps, comments, files, revisions, changelog, tags, links, containers, pins, share links, requests and edit holds",
      "paths": [
        "src/Models/Steps.php",
        "src/Models/Comments.php",
        "src/Models/ImmutableComments.php",
        "src/Models/Uploads.php",
        "src/Models/Revisions.php",
        "src/Models/Changelog.php",
        "src/Models/Tags.php",
        "src/Models/TeamTags.php",
        "src/Models/Links/",
        "src/Models/Pins.php",
        "src/Services/AccessKeyHelper.php",
        "src/Models/RequestActions.php",
        "src/Models/ExclusiveEditMode.php",
        "src/Enums/RequestableAction.php",
        "src/Elabftw/Metadata.php"
      ]
    },
    {
      "description": "Timestamp, signature and export makers",
      "paths": [
        "src/Make/",
        "src/Services/SignatureHelper.php",
        "src/Models/SigKeys.php",
        "src/Controllers/MakeController.php"
      ]
    },
    {
      "description": "Import of .eln and CSV files",
      "paths": [
        "src/Import/"
      ]
    },
    {
      "description": "Scheduler bookings and recurrences",
      "paths": [
        "src/Models/Scheduler.php",
        "src/Models/EventsRecurrence.php",
        "web/scheduler.php"
      ]
    },
    {
      "description": "Compounds database, structure search, inventory and procurement",
      "paths": [
        "src/Models/Compounds.php",
        "src/Models/Fingerprints.php",
        "src/Services/PubChemImporter.php",
        "src/Models/StorageUnits.php",
        "src/Models/ProcurementRequests.php",
        "src/Enums/ProcurementState.php",
        "web/compounds.php",
        "web/chem-editor.php",
        "web/inventory.php",
        "web/team.php"
      ]
    },
    {
      "description": "Search over entries",
      "paths": [
        "src/Services/AdvancedSearchQuery.php",
        "src/Services/AdvancedSearchQuery/"
      ]
    },
    {
      "description": "Accounts, teams, memberships, user groups, batch actions, API keys, to-do lists, instance configuration and audit events",
      "paths": [
        "src/Models/Users/",
        "src/Models/Teams.php",
        "src/Models/Users2Teams.php",
        "src/Models/TeamGroups.php",
        "src/Models/Batch.php",
        "src/Services/UserArchiver.php",
        "src/Services/UserCreator.php",
        "src/Services/TeamsHelper.php",
        "src/Services/UsersHelper.php",
        "src/Models/ApiKeys.php",
        "src/Models/Todolist.php",
        "src/Models/Config.php",
        "src/Models/AuditLogs.php",
        "src/AuditEvent/",
        "src/Enums/AuditCategory.php",
        "src/Services/PasswordValidator.php",
        "src/Enums/PasswordComplexity.php"
      ]
    },
    {
      "description": "Local sign-in with two-factor codes, registration and password reset",
      "paths": [
        "src/Auth/Local.php",
        "src/Auth/UserLoginValidator.php",
        "src/Auth/LoginFlow.php",
        "src/Auth/MfaPolicy.php",
        "src/Auth/MfaVerifier.php",
        "src/Controllers/LoginController.php",
        "web/app/controllers/RegisterController.php",
        "web/app/controllers/ResetPasswordController.php",
        "src/Services/ResetPasswordKey.php",
        "web/change-pass.php"
      ]
    },
    {
      "description": "Web pages, templates and scripts for the mapped areas",
      "paths": [
        "web/experiments.php",
        "web/database.php",
        "web/templates.php",
        "web/resources-templates.php",
        "web/experiments-status.php",
        "web/resources-status.php",
        "web/experiments-categories.php",
        "web/resources-categories.php",
        "web/revisions.php",
        "web/ucp.php",
        "web/profile.php",
        "web/admin.php",
        "web/sysconfig.php",
        "web/login.php",
        "web/register.php",
        "web/app/controllers/UcpController.php",
        "src/Controllers/AbstractEntityController.php",
        "src/templates/",
        "src/ts/"
      ]
    },
    {
      "description": "REST API v2 entry point and routing",
      "paths": [
        "web/app/controllers/ApiController.php",
        "src/Controllers/Apiv2Controller.php",
        "apidoc/v2/openapi.yaml"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Tests",
      "paths": [
        "tests/"
      ]
    },
    {
      "description": "Container images, deployment and CI",
      "paths": [
        "containers/",
        ".github/",
        ".circleci/"
      ]
    },
    {
      "description": "Styles, fonts, translations and static assets",
      "paths": [
        "src/scss/",
        "src/langs/",
        "web/assets/"
      ]
    },
    {
      "description": "The documentation site sources",
      "paths": [
        "documentation/"
      ]
    },
    {
      "description": "The unimplemented API v3 design",
      "paths": [
        "apidoc/v3/",
        "src/Controllers/Apiv3Controller.php"
      ]
    },
    {
      "description": "Demo data population and development seeding",
      "paths": [
        "src/Services/Populate.php",
        "src/tools/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "SAML, LDAP and external sign-in and identity provider management, left out as integrations owned by the identity provider",
      "paths": [
        "src/Auth/Saml.php",
        "src/Auth/Ldap.php",
        "src/Auth/External.php",
        "src/Models/Idps.php",
        "src/Models/IdpsSources.php"
      ]
    },
    {
      "description": "Webhooks, DSpace publication and research organization identifiers, left out as integrations owned by other systems",
      "paths": [
        "src/Models/Webhooks.php",
        "src/Models/TeamsWebhooks.php",
        "src/Models/Dspace.php",
        "src/Models/Teams2Rors.php"
      ]
    },
    {
      "description": "Instance branding and information pages, left out as peripheral presentation",
      "paths": [
        "src/Models/Branding.php",
        "src/Models/Info.php"
      ]
    },
    {
      "description": "Notification inbox and email delivery, left out as delivery of messages the mapped capabilities send",
      "paths": [
        "src/Models/Notifications/",
        "src/Services/Email.php"
      ]
    },
    {
      "description": "Dashboard, left out as a summary of lists mapped elsewhere",
      "paths": [
        "web/dashboard.php",
        "src/Controllers/DashboardController.php"
      ]
    },
    {
      "description": "Usage, scheduler and inventory reports, left out as peripheral reporting",
      "paths": [
        "src/Make/ReportsHandler.php",
        "src/Make/MakeReport.php"
      ]
    },
    {
      "description": "Operator console commands, including bulk timestamping, left out as operator tooling outside the product interfaces",
      "paths": [
        "src/Commands/",
        "bin/"
      ]
    },
    {
      "description": "Upload and step groups, file replacement and archiving, favorite tags and per-user upload lists, left out as organization of content mapped elsewhere",
      "paths": [
        "src/Models/UploadGroups.php",
        "src/Models/StepGroups.php",
        "src/Models/FavTags.php",
        "src/Models/UserUploads.php"
      ]
    },
    {
      "description": "Cancelling or reviewing action requests, left out pending a maintainer view of the Review action",
      "paths": [
        "src/Models/UserRequestActions.php"
      ]
    },
    {
      "description": "Anonymous entry into a team, mapped only as reading what the team publishes",
      "paths": [
        "src/Auth/AnonymousLoginValidator.php"
      ]
    }
  ],
  "limitations": [
    {
      "description": "List filtering by visibility additions, checked against the per-entry permission logic only by reading",
      "paths": [
        "src/Elabftw/EntitySqlBuilder.php"
      ]
    }
  ]
}
---

# Coverage
