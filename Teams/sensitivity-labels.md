---
title: Vertraulichkeitsbezeichnungen für Microsoft Teams
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
description: Erfahren Sie, wie Sie Vertraulichkeitsbezeichnungen verwenden, um Ihre Teams in Microsoft Teams zu schützen.
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937527"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Vertraulichkeitsbezeichnungen für Microsoft Teams

[Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ermöglichen es Teams-Administratoren, den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regeln, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Nachdem Sie Vertraulichkeitsbezeichnungen mit den zugehörigen Richtlinien im [Microsoft Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)konfiguriert haben, können diese Bezeichnungen Teams in Ihrer Organisation zugewiesen werden.

Vertraulichkeitsbezeichnungen werden für Kunden, die Teams Education-SKUs verwenden, derzeit nicht unterstützt. Weitere Informationen zur Lizenzierung finden Sie in der [Beschreibung des Microsoft Teams-Diensts.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Was ist der Unterschied zwischen Vertraulichkeitsbezeichnungen und Teams-Klassifizierungsbezeichnungen?

Vertraulichkeitsbeschriftungen unterscheiden sich von Klassifizierungsbezeichnungen, die auch als Azure AD-Gruppenklassifizierung bezeichnet werden. Klassifizierungsbeschriftungen sind Textzeichenfolgen, die einer Microsoft 365-Gruppe zugeordnet werden können, ihnen aber keine tatsächlichen Richtlinien zugeordnet sind. Sie verwenden Klassifizierungsbezeichnungen als Metadaten und müssen dann andere Methoden wie interne Tools und Skripts verwenden, um Richtlinien zu erzwingen.

Der Vorteil der Verwendung von Vertraulichkeitsbezeichnungen besteht in der automatischen Erzwingung ihrer Richtlinien über eine Kombination der Microsoft 365-Plattform für Gruppen, des Compliance Centers und der Teams-Dienste. Vertraulichkeitsbeschriftungen bieten leistungsfähige Infrastrukturunterstützung zum Sichern der vertraulichen Daten Ihrer Organisation und zur Sicherstellung der Einhaltung Ihrer internen Richtlinien oder Vorschriften.

Wenn Sie derzeit Klassifizierungsbezeichnungen verwenden, finden Sie in der folgenden Dokumentation weitere Informationen und Anweisungen zum Migrieren dieser Bezeichnungen zu Vertraulichkeitsbezeichnungen: Klassische [Azure AD-Gruppenklassifizierung.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>Beispielszenarien für Vertraulichkeitsbeschriftungen

Beispielszenarien für die Verwendung von Vertraulichkeitsbezeichnungen mit Teams in Ihrer Organisation:

- [Festlegen der Datenschutzstufe (öffentlich oder privat) für Teams](#set-the-privacy-level-for-teams)
- [Steuern des Gastzugriffs auf Teams](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Festlegen der Datenschutzstufe für Teams

Sie können eine Vertraulichkeitsbezeichnung erstellen und konfigurieren, die benutzern, wenn sie während der Teamerstellung angewendet werden, ermöglicht, Teams mit einer bestimmten (öffentlichen oder privaten) Datenschutzeinstellung zu erstellen.

Sie erstellen und veröffentlichen z. B. eine Vertraulichkeitsbezeichnung namens "Vertraulich", für die die Option zum Datenschutz der Bezeichnung als privat **konfiguriert ist.** Daher muss jedes Team, das mit dieser Bezeichnung erstellt wird, ein privates Team sein. 

Wenn ein Benutzer ein neues Team  erstellt und die Bezeichnung "Vertraulich" auswählt, steht dem Benutzer nur die Datenschutzoption **"Privat" zur Verfügung.** Andere Datenschutzoptionen wie "Öffentlich" und "Organisationsweit" stehen dem Benutzer nicht zur Auswahl:

![Screenshot der Vertraulichkeitsbezeichnung "Vertraulich"](media/sensitivity-labels-confidential-example.png)

Ebenso erstellen und veröffentlichen Sie eine Vertraulichkeitsbezeichnung namens "Allgemein", für die die Option zum Datenschutz der Bezeichnung als öffentlich konfiguriert **ist.** Wenn ein Benutzer ein neues Team erstellt, kann er öffentliche oder organisationsweite Teams nur erstellen, wenn er diese Bezeichnung auswählt:

![Screenshot der allgemeinen Vertraulichkeitsbeschriftung](media/sensitivity-labels-general-example.png)

Wenn ein Team erstellt wird, wird die Vertraulichkeitsbeschriftung in der oberen rechten Ecke der Kanäle im Team angezeigt.

![Screenshot der Vertraulichkeitsbeschriftung im Teamkanal](media/sensitivity-labels-channel.png)

Ein Teambesitzer kann die Vertraulichkeitsbezeichnung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team geht und dann auf **"Team bearbeiten" klickt.**

![Screenshot der Vertraulichkeitsbeschriftung in Teameigenschaften](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Steuern des Gastzugriffs auf Teams

Sie können Vertraulichkeitsbezeichnungen verwenden, um den Gastzugriff auf Ihre Teams zu steuern. Teams, die mit einer Bezeichnung erstellt wurden, die keinen Gastzugriff erlaubt, sind nur für Benutzer in Ihrer Organisation verfügbar. Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams Admin Center

Sie können Vertraulichkeitsbezeichnungen anwenden, wenn Sie ein Team im Microsoft Teams Admin Center erstellen oder bearbeiten. 

Vertraulichkeitsbezeichnungen sind auch in Teameigenschaften und in der Spalte **"Klassifizierung"** auf der Seite **"Teams verwalten"** im Microsoft Teams Admin Center sichtbar.

## <a name="limitations"></a>Einschränkungen

Bevor Sie Vertraulichkeitsbeschriftungen für Teams verwenden, sollten Sie die folgenden Einschränkungen beachten:

- **Namen von übergeordneten Beschriftungen werden für Unterbezeichnungen nicht angezeigt**
    
    Teams unterstützt Unterbezeichnungen, zeigt jedoch nicht den Namen der übergeordneten Bezeichnung an. Beispielsweise wird **"Alle** \\ **Mitarbeiter vertraulich"** als **"Alle Mitarbeiter" angezeigt.**

- **Vertraulichkeitsbeschriftungen werden von Teams Graph-APIs, PowerShell-Cmdlets und Vorlagen nicht unterstützt.**
    
    Benutzer können keine Vertraulichkeitsbezeichnungen auf Teams anwenden, die direkt über Teams Graph-APIs, Teams-PowerShell-Cmdlets und Teams-Vorlagen erstellt werden.

- **Unterstützung privater Kanäle**
    
    Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeitsbezeichnung, die auf ein Team angewendet wurde. Dieselbe Bezeichnung wird automatisch auf die SharePoint-Websitesammlung für den privaten Kanal angewendet.
    
    Wenn ein Benutzer die Vertraulichkeitsbeschriftung auf einer SharePoint-Website für einen privaten Kanal jedoch direkt ändert, wird diese Bezeichnungsänderung nicht im Teams-Client angezeigt. In diesem Szenario sehen Benutzer weiterhin die ursprüngliche Vertraulichkeitsbezeichnung, die auf das Team angewendet wurde, im Kopf des privaten Kanals.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen für Teams

Befolgen Sie die Anweisungen in der Microsoft 365-Dokumentation, um Vertraulichkeitsbezeichnungen für Teams zu erstellen und zu konfigurieren: 

- [Verwenden Sie Vertraulichkeitsbezeichnungen zum Schützen von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
