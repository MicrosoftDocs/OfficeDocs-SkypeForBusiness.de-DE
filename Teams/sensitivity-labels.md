---
title: Vertraulichkeitsbeschriftungen für Microsoft Teams
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Vertraulichkeitsbezeichnungen verwenden, um Ihre Teams in Ihrer Microsoft Teams.
ms.openlocfilehash: 7602f7ba0a6c8c2908486d02b24d1141d4940a04
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442661"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Vertraulichkeitsbeschriftungen für Microsoft Teams

[Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels) ermöglichen Teams Administratoren, den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regulieren, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Nachdem Sie Vertraulichkeitsbezeichnungen mit den zugehörigen Richtlinien im [Microsoft Compliance Center](/microsoft-365/compliance/go-to-the-securitycompliance-center) konfiguriert haben, können diese Bezeichnungen auf Teams in Ihrer Organisation angewendet werden.

Vertraulichkeitsbezeichnungen werden in Kursteams derzeit für Kunden, die mit Teams Education-SKUs arbeiten, nicht unterstützt. Weitere Informationen zur Lizenzierung finden Sie in der [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>Was ist der Unterschied zwischen Vertraulichkeitsbeschriftungen und Teams Klassifizierung?

Vertraulichkeitsbeschriftungen unterscheiden sich von Teams Klassifizierung, auch bekannt Azure AD Gruppenklassifizierung. Klassifizierungen sind Textzeichenfolgen, die einer Gruppe Microsoft 365 zugeordnet werden können, ihnen aber keine tatsächlichen Richtlinien zugeordnet sind. Sie verwenden die Klassifizierung als Metadaten und müssen dann andere Methoden verwenden, z. B. interne Tools und Skripts, um Richtlinien zu erzwingen.

Der Vorteil der Verwendung von Vertraulichkeitsbezeichnungen besteht in der automatischen Erzwingung ihrer Richtlinien über eine Kombination aus der Microsoft 365 Groups-Plattform, dem Compliance Center und den Teams-Diensten. Vertraulichkeitsbezeichnungen bieten leistungsfähige Infrastrukturunterstützung für die Sicherung der vertraulichen Daten Ihrer Organisation und die Sicherstellung der Einhaltung Ihrer internen Richtlinien oder Vorschriften.

Wenn Sie derzeit eine Teams verwenden, finden Sie in der folgenden Dokumentation weitere Informationen und Anweisungen zum Konvertieren dieser Werte in Vertraulichkeitsbeschriftungen: Klassische [Azure AD-Gruppenklassifizierung](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Beispielszenarien für Vertraulichkeitsbeschriftungen

Beispielszenarien für die Verwendung von Vertraulichkeitsbeschriftungen mit Teams in Ihrer Organisation:

- [Festlegen der Datenschutzstufe (öffentlich oder privat) für Teams](#set-the-privacy-level-for-teams)
- [Steuern des Gastzugriffs auf Teams](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Festlegen der Datenschutzstufe für Teams

Sie können eine Vertraulichkeitsbezeichnung erstellen und konfigurieren, die benutzern, wenn sie während der Teamerstellung angewendet werden, ermöglicht, Teams mit einer bestimmten (öffentlichen oder privaten) Datenschutzeinstellung zu erstellen.

Sie erstellen und veröffentlichen z. B. eine Vertraulichkeitsbezeichnung mit dem Namen "Vertraulich", für die die Datenschutzoption für die Bezeichnung als Privat konfiguriert **ist**. Daher muss jedes Team, das mit dieser Bezeichnung erstellt wird, ein privates Team sein. 

Wenn ein Benutzer ein neues Team erstellt und die Bezeichnung Vertraulich  auswählt, steht dem Benutzer als einzige Datenschutzoption nur Privat **zur Verfügung**. Andere Datenschutzoptionen wie "Öffentlich" und "Organisationsweit" stehen dem Benutzer nicht zur Auswahl:

![Screenshot der Vertraulichkeitsbezeichnung "Vertraulich".](media/sensitivity-labels-confidential-example.png)

Ebenso erstellen und veröffentlichen Sie eine Vertraulichkeitsbezeichnung namens "Allgemein", für die die Datenschutzoption für die Bezeichnung als öffentlich konfiguriert **ist**. Wenn ein Benutzer ein neues Team erstellt, kann er öffentliche oder organisationsweite Teams nur erstellen, wenn er diese Bezeichnung auswählt:

![Screenshot of General sensitivity label.](media/sensitivity-labels-general-example.png)

Wenn das Team erstellt wird, ist die Vertraulichkeitsbezeichnung für Benutzer in der oberen rechten Ecke von Kanälen im Team sichtbar. 

![Screenshot der Vertraulichkeitsbezeichnung im Teamkanal.](media/sensitivity-labels-channel.png)

Ein Teambesitzer kann die Vertraulichkeitsbezeichnung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team wechseln und dann auf **Team bearbeiten klickt**.

![Screenshot der Vertraulichkeitsbeschriftung in Teameigenschaften](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Steuern des Gastzugriffs auf Teams

Sie können Vertraulichkeitsbezeichnungen verwenden, um den Gastzugriff auf Ihre Teams zu steuern. Teams mit einer Bezeichnung erstellt wurden, die den Gastzugriff nicht erlaubt, stehen nur Benutzern in Ihrer Organisation zur Verfügung. Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams Admin Center

Sie können Vertraulichkeitsbezeichnungen anwenden, wenn Sie ein Team im Microsoft Teams Admin Center erstellen oder bearbeiten. 

Vertraulichkeitsbeschriftungen sind auch in Teameigenschaften und in der Spalte **Klassifizierung** auf der Seite Teams verwalten im Microsoft Teams Admin Center sichtbar.

## <a name="limitations"></a>Einschränkungen

Bevor Sie Vertraulichkeitsbeschriftungen Teams, sollten Sie die folgenden Einschränkungen beachten:

- **Vertraulichkeitsbeschriftungen werden von den APIs Teams Graph PowerShell-Cmdlets nicht unterstützt.**
    
    Benutzer können beim Erstellen von Teams keine Vertraulichkeitsbezeichnungen direkt über Teams Graph-APIs oder Teams PowerShell-Cmdlets angeben. Moderne Gruppen und Graph-APIs und PowerShell-Cmdlets ermöglichen jedoch das Erstellen von Gruppen mit Vertraulichkeitsbezeichnungen. Das bedeutet, dass Sie mit diesen Methoden Gruppen mit Vertraulichkeitsbeschriftungen erstellen und diese Gruppen dann in Teams konvertieren können.

- **Unterstützung privater Kanäle**
    
    Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeitsbezeichnung, die auf ein Team angewendet wurde. Die gleiche Bezeichnung wird automatisch auf die SharePoint für den privaten Kanal angewendet.
    
    Wenn ein Benutzer die Vertraulichkeitsbeschriftung auf einer SharePoint-Website für einen privaten Kanal jedoch direkt ändert, wird diese Änderung nicht im Client für Teams widerspiegelt. In diesem Szenario sehen Benutzer weiterhin die ursprüngliche Vertraulichkeitsbezeichnung, die auf das Team angewendet wurde, im Kopf des privaten Kanals.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen für Teams

Befolgen Sie die Anweisungen in der Microsoft 365, um Vertraulichkeitsbeschriftungen für Ihre Dokumente zu erstellen Teams: 

- [Verwenden Sie Vertraulichkeitsbezeichnungen, um Inhalte in Microsoft Teams, Microsoft 365 Gruppen und SharePoint zu schützen](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
