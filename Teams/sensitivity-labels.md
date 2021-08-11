---
title: Vertraulichkeitsbeschriftungen für Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
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
description: Erfahren Sie, wie Sie Vertraulichkeitsbezeichnungen verwenden, um Ihre Teams in Ihrer Microsoft Teams.
ms.openlocfilehash: 407b5f09322cf00e4dfe7a29bd513caa7476623cfeac5099019cc2c3ffb6a248
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275941"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Vertraulichkeitsbeschriftungen für Microsoft Teams

[Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels) ermöglichen Teams, den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regulieren, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Nachdem Sie Vertraulichkeitsbezeichnungen mit den zugehörigen Richtlinien im [Microsoft Compliance Center](/microsoft-365/compliance/go-to-the-securitycompliance-center)konfiguriert haben, können diese Bezeichnungen auf Teams in Ihrer Organisation angewendet werden.

Vertraulichkeitsbezeichnungen werden derzeit in Kursteams für Kunden, die ihre Education-SKUs Teams, nicht unterstützt. Weitere Informationen zur Lizenzierung finden Sie in der [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Was ist der Unterschied zwischen Vertraulichkeitsbeschriftungen und Teams Klassifizierungsbezeichnungen?

Vertraulichkeitsbeschriftungen unterscheiden sich von Klassifizierungsbezeichnungen, die auch als Azure AD-Gruppenklassifizierung bezeichnet werden. Bei Klassifizierungsbeschriftungen handelt es sich um Textzeichenfolgen, die einer Gruppe Microsoft 365 zugeordnet werden können, der aber keine tatsächlichen Richtlinien zugeordnet sind. Sie verwenden Klassifizierungsbezeichnungen als Metadaten und müssen dann andere Methoden verwenden, z. B. interne Tools und Skripts, um Richtlinien zu erzwingen.

Der Vorteil der Verwendung von Vertraulichkeitsbezeichnungen besteht in der automatischen Erzwingung ihrer Richtlinien über eine Kombination aus der Microsoft 365 Groups-Plattform, dem Compliance Center und den Teams-Diensten. Vertraulichkeitsbezeichnungen bieten leistungsstarke Infrastrukturunterstützung für die Sicherung der vertraulichen Daten Ihrer Organisation und die Sicherstellung der Einhaltung Ihrer internen Richtlinien oder Vorschriften.

Wenn Sie derzeit Klassifizierungsbezeichnungen verwenden, finden Sie in der folgenden Dokumentation weitere Informationen und Anweisungen zum Migrieren dieser Bezeichnungen zu Vertraulichkeitsbeschriftungen: [Klassische Azure AD-Gruppenklassifizierung](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Beispielszenarien für Vertraulichkeitsbeschriftungen

Beispielszenarien für die Verwendung von Vertraulichkeitsbeschriftungen mit Teams in Ihrer Organisation:

- [Festlegen der Datenschutzstufe (öffentlich oder privat) für Teams](#set-the-privacy-level-for-teams)
- [Steuern des Gastzugriffs auf Teams](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Festlegen der Datenschutzstufe für Teams

Sie können eine Vertraulichkeitsbezeichnung erstellen und konfigurieren, die benutzern, wenn sie während der Teamerstellung angewendet werden, ermöglicht, Teams mit einer bestimmten (öffentlichen oder privaten) Datenschutzeinstellung zu erstellen.

Sie erstellen und veröffentlichen z. B. eine Vertraulichkeitsbezeichnung mit dem Namen "Vertraulich", für die die Datenschutzoption für die Bezeichnung als Privat **konfiguriert ist.** Daher muss jedes Team, das mit dieser Bezeichnung erstellt wird, ein privates Team sein. 

Wenn ein Benutzer ein neues Team  erstellt und die Bezeichnung Vertraulich auswählt, steht dem Benutzer als einzige Datenschutzoption nur Privat **zur Verfügung.** Andere Datenschutzoptionen wie "Öffentlich" und "Organisationsweit" stehen dem Benutzer nicht zur Auswahl:

![Screenshot der Vertraulichkeitsbezeichnung "Vertraulich"](media/sensitivity-labels-confidential-example.png)

Ebenso erstellen und veröffentlichen Sie eine Vertraulichkeitsbezeichnung mit dem Namen "Allgemein", für die die Datenschutzoption für die Bezeichnung als öffentlich **konfiguriert ist.** Wenn ein Benutzer ein neues Team erstellt, kann er öffentliche oder organisationsweite Teams nur erstellen, wenn er diese Bezeichnung auswählt:

![Screenshot of General sensitivity label](media/sensitivity-labels-general-example.png)

Wenn das Team erstellt wird, wird die Vertraulichkeitsbeschriftung in der oberen rechten Ecke der Kanäle im Team angezeigt. 

> [!NOTE]
> Wenn Sie hierarchische Beschriftungen mit über- und untergeordneten Ebenen wie "Vertraulich\Finanzen" verwenden, wird nur die übergeordnete Beschriftung in der Kanalüberschrift angezeigt.

![Screenshot der Vertraulichkeitsbezeichnung im Teamkanal](media/sensitivity-labels-channel.png)

Ein Teambesitzer kann die Vertraulichkeitsbezeichnung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team geht und dann **auf Team bearbeiten klickt.**

![Screenshot der Vertraulichkeitsbezeichnung in Teameigenschaften](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Steuern des Gastzugriffs auf Teams

Sie können Vertraulichkeitsbezeichnungen verwenden, um den Gastzugriff auf Ihre Teams zu steuern. Teams mit einer Bezeichnung erstellt wurden, die keinen Gastzugriff erlaubt, stehen nur Benutzern in Ihrer Organisation zur Verfügung. Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams Admin Center

Sie können Vertraulichkeitsbezeichnungen anwenden, wenn Sie ein Team im Microsoft Teams Admin Center erstellen oder bearbeiten. 

Vertraulichkeitsbeschriftungen sind auch in Teameigenschaften  und in der Spalte **Klassifizierung** auf der Seite Teams verwalten im Microsoft Teams Admin Center sichtbar.

## <a name="limitations"></a>Einschränkungen

Bevor Sie Vertraulichkeitsbeschriftungen für Teams verwenden, sollten Sie die folgenden Einschränkungen beachten:

- **Namen von übergeordneten Beschriftungen werden für Unterbezeichnungen nicht angezeigt**
    
    Teams unterstützt Unterbezeichnungen, zeigt aber nicht den Namen der übergeordneten Bezeichnung an. Beispielsweise wird **"Vertraulich** \\ **alle Mitarbeiter"** als **"Alle Mitarbeiter" angezeigt.**

- **Vertraulichkeitsbeschriftungen werden von den Teams Graph, PowerShell-Cmdlets und Vorlagen nicht unterstützt.**
    
    Benutzer können beim Erstellen von Teams keine Vertraulichkeitsbezeichnungen direkt über Teams Graph-APIs, Teams PowerShell-Cmdlets und Teams angeben. Moderne Gruppen und Graph-APIs und PowerShell-Cmdlets ermöglichen jedoch das Erstellen von Gruppen mit Bezeichnungen. Daher können Benutzer zunächst gruppen mit Bezeichnungen mithilfe von Groups Graph-APIs oder PowerShell-Cmdlets erstellen und diese Gruppen dann in das -Teams.

- **Unterstützung privater Kanäle**
    
    Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeitsbezeichnung, die auf ein Team angewendet wurde. Die gleiche Bezeichnung wird automatisch auf die SharePoint für den privaten Kanal angewendet.
    
    Wenn ein Benutzer die Vertraulichkeitsbezeichnung auf einer SharePoint-Website für einen privaten Kanal jedoch direkt ändert, wird diese Änderung nicht im Client für Teams angezeigt. In diesem Szenario sehen Benutzer weiterhin die ursprüngliche Vertraulichkeitsbezeichnung, die auf das Team angewendet wurde, im Kopf des privaten Kanals.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen für Teams

Befolgen Sie die Anweisungen in der Microsoft 365, um Vertraulichkeitsbeschriftungen für Ihre Dokumente zu erstellen Teams: 

- [Verwenden Sie Vertraulichkeitsbezeichnungen,](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)um Inhalte in Microsoft Teams, Microsoft 365 Gruppen und SharePoint zu schützen.
