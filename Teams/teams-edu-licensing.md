---
title: Microsoft Teams-Ressourcen für Administratoren in Bildungseinrichtungen
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Exemplarische Vorgehensweise für die Lizenzierung von Microsoft Teams für Bildungseinrichtungen.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7d5ebd0552aafffe2eb2330e6945f99dd788b2f
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858630"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a>Zuweisen von Microsoft Teams-Lizenzen für Bildungseinrichtungen

Microsoft Teams ist ein digitaler Hub, der Unterhaltungen, Inhalte und Apps an einem zentralen Ort zusammenbringt. Da es auf Office 365 basiert, profitieren Bildungseinrichtungen von der Integration in die vertrauten Office-Apps und -Dienste. Mit Microsoft Teams kann Ihre Institution gemeinsame Kursräume erstellen, sich in professionellen Lerngemeinschaften (Professional Learning Communities, PLCs) verbinden und mit den Mitarbeitern ihrer Bildungseinrichtung kommunizieren – alles das über eine einzige Benutzeroberfläche in Office 365 Education.

Zum Einstieg müssen IT-Administratoren das Microsoft 365 Admin Center verwenden, um [Microsoft Teams für ihre Bildungseinrichtung zu aktivieren](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
Anschließend müssen Sie den Benutzerkonten Lizenzen zuweisen, damit ihre Lehrkräfte, Mitarbeiter und Schüler/Studenten auf Office 365-Dienste wie Microsoft Teams zugreifen können.

Sie können Benutzerkonten Lizenzen entweder einzeln oder automatisch über eine Gruppenmitgliedschaft zuweisen. In diesem Artikel erfahren Sie, wie Sie einem einzelnen Benutzer oder einer kleinen Gruppe von Benutzerkonten über das Microsoft 365 Admin Center Office 365-Lizenzen zuweisen. Informationen zum automatischen Zuweisen von Lizenzen über eine Gruppenmitgliedschaft finden Sie in den folgenden Artikeln:

- [Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [Gruppenbasierte Lizenzierung in Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

Sie können Benutzern entweder auf der Seite **Lizenzen** oder auf der Seite **Aktive Benutzer** Lizenzen zuweisen. Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für bestimmte Produkte zuweisen möchten.

> [!NOTE]
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Benutzern auf der Seite "Lizenzen" Lizenzen zuweisen

> [!NOTE]
> Sie müssen globaler Administrator, Abrechnungsadministrator, Lizenzadministrator oder Benutzerverwaltungsadministrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen. Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, für die Sie über Abonnements verfügen. Außerdem sehen Sie hier die Gesamtzahl der Lizenzen für jedes Produkt und erfahren, wie viele Lizenzen zugewiesen und wie viele verfügbar sind.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > [Lizenzen](https://go.microsoft.com/fwlink/p/?linkid=842264).

   ![Screenshot des Abrechnungsfensters und der Menüoptionen.](media/EDU-Lic-Billing-License.png)
2. Wählen Sie ein Produkt aus, für das Sie Lizenzen zuweisen möchten. Microsoft Teams ist ein Bestandteil der kostenlosen Office 365 A1 für Schüler und Studenten-SKU.

   ![Screenshot der Seite "Lizenzen" mit verfügbaren Produkten, deren Lizenzen Sie zuweisen können.](media/EDU-Lic-Licenses-Products.png)
3. Wählen Sie **Lizenzen zuweisen** aus.

   ![Screenshot des Abschnitts "Benutzer" der Seite und der Option "Lizenzen zuweisen" mit einem Pluszeichen davor.](media/EDU-Lic-Assign-Licenses.png)
4. Beginnen Sie im Bereich **Benutzern Lizenzen zuweisen** mit der Eingabe eines Namens, um eine Liste von Namen anzuzeigen. Wählen Sie den gewünschten Namen aus den Ergebnissen aus, um ihn der Liste hinzuzufügen. Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.

   ![Screenshot der Seite "Benutzern Lizenzen zuweisen" mit einem teilweise eingegebenen Namen und den eingeblendeten Suchergebnissen für diesen Teilnamen.](media/EDU-Lic-Assign-Licenses-Users.png)
5. Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um den Zugriff auf bestimmte Elemente, z. B. Microsoft Teams, zuzuweisen oder zu entfernen. Stellen Sie sicher, dass **Microsoft Teams** und **Office für das Web (Education)** ausgewählt sind.
6. Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.

So ändern Sie die Apps und Dienste, auf die ein Benutzer zugreifen kann

1. Wählen Sie die Zeile aus, die den Benutzer enthält.
1. Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.
1. Wählen Sie abschließend **Speichern** und dann **Schließen** aus.

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a>Zuweisen von Lizenzen zu einem oder mehreren Benutzern auf der Seite "Aktive Benutzer"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** > [Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822).

   ![Screenshot der Menüoption "aktive Benutzer" im Microsoft O365 Admin Center.](media/EDU-Lic-Active-Users.png)
2. Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.

   ![Screenshot der Seite "Aktive Benutzer" und einer Liste der aktiven Benutzer auf dieser Seite, wobei einige Benutzer ausgewählt sind (der Kreis neben ihren Namen ist ausgefüllt).](media/EDU-Lic-Active-Users-List.png)
3. Wählen Sie am oberen Rand **Produktlizenzen verwalten** aus.

   ![Screenshot der Registerkarte "Produktlizenzen verwalten", darunter ein Benutzer, der als "nicht lizenziert" angegeben ist.](media/EDU-Lic-Manage-Product-Licenses.png)
4. Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** > **Weiter** aus.

   ![Screenshot des Fensters "Produktlizenzen verwalten" mit ausgewähltem Optionsfeld "Zu vorhandenen Produktlizenzzuweisungen hinzufügen".](media/EDU-Lic-Add-Existing-Product.png)
5. Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**. Stellen Sie sicher, dass **Microsoft Teams** und **Office für das Web (Education)** ausgewählt sind.

   ![Screenshot von Microsoft Teams und Office für das Web (Education), ausgewählt auf der Registerkarte "Zu vorhandenen Produkten hinzufügen".](media/EDU-Lic-Add-Existing-Products.png)

   Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für die Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.
6. Wählen Sie am unteren Rand des Bereichs "Hinzufügen" > "Schließen" aus.
