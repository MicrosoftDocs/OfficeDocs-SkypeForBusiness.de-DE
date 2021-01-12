---
title: Vertraulichkeitsbezeichnungen für Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Vertraulichkeitsbeschriftungen in Microsoft Teams definieren und verwenden.
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795774"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Vertraulichkeitsbezeichnungen für Microsoft Teams

[Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ermöglichen es Teams-Administratoren, den Zugriff auf vertrauliche Organisationsinhalte zu regeln, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Sie können Vertraulichkeitsbeschriftungen und die zugehörigen Richtlinien im [Compliance Center definieren.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) Diese Bezeichnungen und Richtlinien werden automatisch auf Teams in Ihrer Organisation angewendet.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Was ist der Unterschied zwischen Vertraulichkeitsbezeichnungen und Teams-Klassifizierungsbezeichnungen?

Vertraulichkeitsbeschriftungen unterscheiden sich von Klassifizierungsbezeichnungen. Klassifizierungsbeschriftungen sind Textzeichenfolgen, die einer Microsoft 365-Gruppe zugeordnet werden können, ihnen aber keine tatsächlichen Richtlinien zugeordnet sind. Klassifizierungsbezeichnungen werden als Metadaten verwendet, um Richtlinien manuell über interne Tools und Skripts zu erzwingen.

Andererseits werden Vertraulichkeitsbeschriftungen und ihre Richtlinien automatisch über eine Kombination der Gruppenplattform, des Security & Compliance Centers und der Teams-Dienste erzwungen. Vertraulichkeitsbeschriftungen bieten leistungsstarke Infrastrukturunterstützung zum Sichern der vertraulichen Daten Ihrer Organisation.  

Um Ihre vorhandenen Gruppen von der Verwendung von Klassifizierungsbezeichnungen zur Verwendung von Vertraulichkeitsbeschriftungen zu migrieren, befolgen Sie die Anweisungen in Azure Active Directory-Klassifizierung und Vertraulichkeitsbezeichnungen für [Microsoft 365-Gruppen.](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Erstellen, Verwalten und Veröffentlichen von Vertraulichkeitsbezeichnungen für Teams

Informationen zum Aktivieren, Erstellen und Veröffentlichen von Vertraulichkeitsbezeichnungen für Teams finden Sie unter Verwenden von Vertraulichkeitsbezeichnungen zum Schützen von [Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

>[!IMPORTANT]
>Das Erstellen, Aktualisieren und Löschen von Vertraulichkeitsbeschriftungen erfordert eine sorgfältige Reihenfolge mit der Veröffentlichung von Bezeichnungen für Benutzer. Jede Abweichung in der Sequenz kann zu dauerhaften Teamerstellungsfehlern für alle Benutzer führen. Daher ist es wichtig, die folgenden Schritte zu <a href="#modifydeletelabels"></a>unternehmen, wenn Sie Bezeichnungen erstellen und <a href="#createpublishlabels">veröffentlichen,</a>veröffentlichte Bezeichnungen ändern und löschen sowie Fehler bei der <a href="#manageerrors">Teamerstellung verwalten.</a>

**Erstellen und Veröffentlichen von Bezeichnungen** <a name="createpublishlabels"></a>

Wenn eine Bezeichnung im Compliance Center erstellt und veröffentlicht wird, kann es bis zu 10 Minuten dauern, bis die Bezeichnung auf der Teamerstellungsoberfläche angezeigt wird. Verwenden Sie die folgenden Schritte, um die Bezeichnung für alle Benutzer im Mandanten zu veröffentlichen:
1. Erstellen Sie die Bezeichnung, und veröffentlichen Sie sie für einige ausgewählte Benutzerkonten im Mandanten.
2. Warten Sie nach der Veröffentlichung der Bezeichnung 10 Minuten.
3. Versuchen Sie nach 10 Minuten, mithilfe eines der Benutzerkonten, die Zugriff auf die Bezeichnung haben, ein Team mit der Bezeichnung zu erstellen.
4. Wenn das Team in Schritt 3 erfolgreich erstellt wurde, fahren Sie fort, und veröffentlichen Sie die Bezeichnung für die verbleibenden Benutzer im Mandanten.

**Ändern und Löschen veröffentlichter Bezeichnungen** <a name="modifydeletelabels"></a>

Das Löschen oder Ändern der Bezeichnung, während sie Vertraulichkeitsrichtlinien zugeordnet ist, kann zu Teamerstellungsfehlern im gesamten Mandanten führen. Daher müssen Sie vor dem Löschen oder Ändern einer Bezeichnung zuerst die Zuordnung der Bezeichnung von den zugehörigen Richtlinien entfernen. Verwenden Sie die folgenden Schritte  
um eine Bezeichnung zu löschen oder zu ändern:
1. Entfernen Sie die Bezeichnung aus allen Richtlinien, die diese Bezeichnung verwenden. Alternativ können Sie auch die Richtlinien selbst löschen.
2. Wenn die Bezeichnung aus den Richtlinien entfernt wird oder die Richtlinien selbst gelöscht werden, warten Sie 10 Minuten, bevor Sie fortfahren.
3. Starten Sie nach 10 Minuten die Teamerstellungsschnittstelle, und stellen Sie sicher, dass die Bezeichnung für keinen Benutzer im Mandanten mehr sichtbar ist.
4. Jetzt können Sie die Bezeichnung bedenkenlos löschen oder ändern.

**Verwalten von Teamerstellungsfehlern** <a name="manageerrors"></a>

Wenn die Teamerstellung zu irgendeinem Zeitpunkt während der öffentlichen Vorschau fehlschlägt, haben Sie zwei Möglichkeiten:
 - Stellen Sie sicher, dass vertraulichkeitsbeschriftungen für keinen Benutzer während der Teamerstellung obligatorisch sind.
 - Deaktivieren Sie Vertraulichkeitsbeschriftungen mithilfe der Skripts in ["Diese Vorschau aktivieren".](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)

Beachten Sie, dass die Einstellung "EnableMIPLabels" wie folgt auf "false" festgelegt werden muss:

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Verwenden von Vertraulichkeitsbeschriftungen mit Teams

Hier sind einige Beispielszenarien, wie Sie Vertraulichkeitsbeschriftungen in Teams in Ihrer Organisation verwenden können.

### <a name="privacy-setting-of-teams"></a>Datenschutzeinstellungen von Teams

Sie können eine Vertraulichkeitsbezeichnung erstellen, die Es Benutzern ermöglicht, Teams mit einer bestimmten (öffentlichen oder privaten) Einstellung zu erstellen, wenn diese während der Teamerstellung angewendet werden.

Sie erstellen z. B. im Security & Compliance Center die Bezeichnung "Vertraulich" und konfigurieren Teams so, dass jedes Team, das mit dieser Bezeichnung erstellt wird, ein privates Team sein muss. Wenn ein Benutzer ein neues Team  erstellt und die Bezeichnung "Vertraulich" auswählt, steht dem Benutzer nur die Datenschutzoption **"Privat" zur Verfügung.** Andere Datenschutzoptionen wie "Öffentlich" und "Organisationsweit" sind für den Benutzer deaktiviert.

![Screenshot der Vertraulichkeitsbezeichnung "Vertraulich"](media/sensitivity-labels-confidential-example.png)

Wenn der Benutzer beim  Erstellen eines neuen Teams "Allgemein" auswählt, kann er nur öffentliche oder organisationsweite Teams erstellen.

![Screenshot der allgemeinen Vertraulichkeitsbeschriftung](media/sensitivity-labels-general-example.png)

Wenn das Team erstellt wird, wird die Vertraulichkeitsbeschriftung in der oberen rechten Ecke der Kanäle im Team angezeigt.

![Screenshot der Vertraulichkeitsbeschriftung im Teamkanal](media/sensitivity-labels-channel.png)

Ein Teambesitzer kann die Vertraulichkeitsbezeichnung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team geht und dann auf "Team **bearbeiten" klickt.**

![Screenshot der Vertraulichkeitsbeschriftung in Teameigenschaften](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Gastzugriff auf Teams

Sie können angeben, ob ein Team, das mit einer bestimmten Bezeichnung erstellt wurde, Gastzugriff zulässt. Teams, die mit einer Bezeichnung erstellt wurden, die keinen Gastzugriff erlaubt, sind nur für Benutzer in Ihrer Organisation verfügbar. Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Vertraulichkeitsbezeichnungen im Microsoft Teams Admin Center

Sie können Vertraulichkeitsbezeichnungen festlegen, wenn Sie ein Team im Microsoft Teams Admin Center erstellen oder bearbeiten. Vertraulichkeitsbeschriftungen sind auch in Teameigenschaften und in der Spalte **"Klassifizierung"** auf der Seite "Teams verwalten" im Microsoft Teams Admin Center sichtbar.

## <a name="known-issues"></a>Bekannte Probleme

**Unterstützung für Vertraulichkeitsbeschriftungen in Teams Graph-APIs, PowerShell-Cmdlets und -Vorlagen**

Derzeit können Benutzer keine Vertraulichkeitsbeschriftungen auf Teams anwenden, die direkt über Graph-APIs, PowerShell-Cmdlets und Vorlagen erstellt werden.

**Unterstützung für Vertraulichkeitsbeschriftungen in Teams EDU-SKUs**

Vertraulichkeitsbezeichnungen werden für Kunden, die Teams Education-SKUs verwenden, derzeit nicht unterstützt.

**Bearbeiten von Vertraulichkeitsbeschriftungen direkt in einer SharePoint-Websitesammlung für private Kanäle**

Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeitsbezeichnung, die auf ein Team angewendet wurde. Darüber hinaus wird dieselbe Bezeichnung automatisch auf die SharePoint-Websitesammlung für den privaten Kanal angewendet.

Wenn ein Benutzer die Vertraulichkeitsbezeichnung in einer SharePoint-Websitesammlung für einen privaten Kanal direkt aktualisiert, wird diese Bezeichnung im Teamclient nicht aktualisiert. In diesem Szenario sehen Benutzer weiterhin die vertraulichkeitsbeschriftung, die auf ein Team angewendet wurde, in der Kopfzeile des privaten Kanals.

**Weitergabezeiten für Änderungen, die auf Vertraulichkeitsbezeichnungen außerhalb der Teams-App angewendet wurden**

Es kann bis zu 24 Stunden dauern, bis Änderungen an Vertraulichkeitsbeschriftungen außerhalb der Teams-App in der App "Teams" angezeigt werden. Dies gilt für alle Änderungen, die zum Aktivieren oder Deaktivieren von Bezeichnungen für einen Mandanten, änderungen an Bezeichnungsnamen, Einstellungen und Richtlinien vorgenommen wurden.

Darüber hinaus kann es bis zu 24 Stunden dauern, bis alle Änderungen an einer Bezeichnung, die direkt an einer Gruppe oder einer SharePoint-Websitesammlung, die das Team unterstützt, vorgenommen wurden, an die App "Teams" weitervererbt werden.
