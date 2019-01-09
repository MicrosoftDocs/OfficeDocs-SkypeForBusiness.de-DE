---
title: Hinzufügen eines Gasts zu einem Team
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Hier lernen Sie die verfügbaren Tools kennen, mit denen Administratoren neue Gastbenutzer zu einer Organisation hinzufügen können. Dies schließt den Microsoft Teams-Desktop, Webclients und das Portal für Azure Active Directory B2B-Zusammenarbeit ein.
appliesto:
- Microsoft Teams
ms.openlocfilehash: efd44fade33f611148dc2ab4ca9afb4040705123
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772741"
---
<a name="add-a-guest-to-a-team"></a>Hinzufügen eines Gasts zu einem Team
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Jeder Benutzer mit einer Business "oder" Consumer e-Mail-Konto, wie Outlook, Google Mail oder andere, kann als Gast in Teams teilnehmen.


Als globaler Administrator können Sie einen neuen Gastbenutzer auf unterschiedliche Weise zur Organisation hinzufügen: 
- Globale Administratoren können mit dem Desktop- oder Webclient von Microsoft Teams einen Gast zu einem Team hinzufügen.
- Fügen Sie Gäste über Azure Active Directory B2B-Zusammenarbeit zu Ihrer Organisation hinzu. Azure Active Directory B2B-Zusammenarbeit ermöglicht es einem globalen Administrator, eine Reihe externer Benutzer einzuladen und zu autorisieren, indem er eine CSV-Datei (durch Trennzeichen getrennte Werte) mit nicht mehr als 2.000 Zeilen in das Portal für B2B-Zusammenarbeit hochlädt. Ausführlichere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=826383).



Mit Azure Active Directory B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen. Diese Richtlinien können auf der Mandanten-, App- oder individuellen Benutzerebene genau so erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden. Solche Richtlinien werden bei der Ressourcenorganisation erzwungen. Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/?linkid=857454). Einzelne Gastbenutzer können nicht blockiert werden.



Gast-Benutzer aus, die Sie bereits über Azure Active Directory B2B, Office 365 Gruppen oder SharePoint Online hinzugefügt haben, sind bereit. Der Office 365-Administrator oder ein Teambesitzer kann diese Gäste zu den jeweiligen Teams hinzufügen. Wenn ein Team bereits zu einer Office 365-Gruppe gehört und ein Gast zur Gruppe hinzugefügt wird, erhält der Gast Zugriff auf das Team. Wenn ein Gast über die Office 365-Gruppe hinzugefügt wird, erhält der Gast keine Einladungs-E-Mail. Ein Mitglied des Teams sollte den Gast daher benachrichtigen.

> [!NOTE]
> Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.



In Azure Active Directory oder im Office 365 Security &amp; Compliance Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen. Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert. Nähere Einzelheiten finden Sie unter [Überwachung eines B2B-Zusammenarbeitsbenutzers und Berichterstellung](https://go.microsoft.com/fwlink/p/?linkid=858884) und [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="more-information"></a>Weitere Informationen

[Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md)</br>
[Aktivieren Sie oder Deaktivieren der Gast Access in Microsoft-Teams](set-up-guests.md)</br>
[Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team](guest-access-powershell.md)