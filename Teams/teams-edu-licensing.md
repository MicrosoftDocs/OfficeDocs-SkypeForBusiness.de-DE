---
title: Zuweisen von Microsoft Teams-Lizenzen für Bildungseinrichtungen
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Erfahren Sie, wie Sie Lizenzen für Microsoft Teams für Education zuweisen.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426802"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>Zuweisen von Microsoft Teams-Lizenzen für Bildungseinrichtungen

Dieser Artikel richtet sich an IT-Administratoren in Bildungseinrichtungen, die Ihren Lehrkräften, Mitarbeitern und Studenten Teamlizenzen zuweisen müssen.

Um Ihre Benutzer auf Teams vorzubereiten, müssen Sie Folgendes ausführen:

1. [Aktivieren Sie Microsoft Teams für Ihre Schule im Microsoft 365 Admin Center](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
2. Zuweisen von Lizenzen zu Benutzerkonten für den Zugriff auf Microsoft 365-Dienste, einschließlich Teams.

## <a name="ways-to-assign-teams-licenses"></a>Möglichkeiten zum Zuweisen von Teams-Lizenzen

Sie können Benutzerkonten Lizenzen zuweisen:

- Einzeln oder für eine kleine Gruppe von Benutzern im Microsoft 365 Admin Center.
- Automatisches Durchlaufen der Gruppenmitgliedschaft mithilfe von [PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) oder [der gruppenbasierten Active Directory-Lizenzierung](/azure/active-directory/users-groups-roles/licensing-groups-assign).

In diesem Artikel erfahren Sie, wie Sie Lizenzen im Microsoft 365 Admin Center zuweisen.

In der Microsoft 365 Admin Center können Sie Benutzern Lizenzen zuweisen:

- Die Seite **"Lizenzen** ", um bestimmten Benutzern Produktlizenzen zuzuweisen.
- Die Seite **"Aktive Benutzer"** zum Zuweisen von Benutzerlizenzen zu bestimmten Produkten.

> [!NOTE]
> Sie müssen globaler Administrator, Abrechnungsadministrator, Lizenzadministrator oder Benutzerverwaltungsadministrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Office 365](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Benutzern auf der Seite "Lizenzen" Lizenzen zuweisen

Auf der Seite **"Lizenzen** " wird eine Liste aller Produkte angezeigt, für die Sie Abonnements haben, die Gesamtanzahl der Lizenzen für jedes Produkt, wie viele Lizenzen zugewiesen sind und wie viele verfügbar sind.

1. Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) zur Seite "[Abrechnungslizenzen](https://go.microsoft.com/fwlink/p/?linkid=842264) > ".

2. Wählen Sie ein Produkt aus, für das Sie Lizenzen zuweisen möchten. Microsoft Teams ist Teil der kostenlosen Microsoft 365 A1 für Studenten-SKU.

3. Wählen Sie **Lizenzen zuweisen** aus.

4. Beginnen Sie im Bereich **Benutzern Lizenzen zuweisen** mit der Eingabe eines Namens, um eine Liste von Namen anzuzeigen.

5. Wählen Sie den gewünschten Namen aus den Ergebnissen aus, um ihn der Liste hinzuzufügen. Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.

6. Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um den Zugriff auf bestimmte Elemente, z. B. Microsoft Teams, zuzuweisen oder zu entfernen. Stellen Sie sicher, dass **Microsoft Teams** und **Office für das Web (Education)** ausgewählt sind.

7. Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>Ändern der Apps und Dienste, auf die ein Benutzer Zugriff hat

1. Wählen Sie die Zeile aus, die den Benutzer enthält.

2. Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.

3. Wählen Sie abschließend **Speichern** und dann **Schließen** aus.

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>Zuweisen von Lizenzen zu Benutzern auf der Seite "Aktive Benutzer"

1. Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) zur Seite "[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822) > ".

2. Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.

3. Wählen Sie oben die Option " **Produktlizenzen verwalten" aus**.

4. Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** > **Weiter** aus.

5. Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**. Stellen Sie sicher, dass **Microsoft Teams** und **Office für das Web (Education)** ausgewählt sind.

   Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für die Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.

6. Wählen Sie unten im Bereich "**Schließen" aus** > **.**
