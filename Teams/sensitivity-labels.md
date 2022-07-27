---
title: Vertraulichkeitsbezeichnungen für Microsoft Teams
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
description: Erfahren Sie, wie Sie Vertraulichkeitsbezeichnungen verwenden, um Ihre Teams in Microsoft Teams zu schützen.
ms.openlocfilehash: 6bbeb4d804c9f397936d331df902cc295d044d75
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023772"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Vertraulichkeitsbezeichnungen für Microsoft Teams

[Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels) ermöglichen Es Teams-Administratoren, den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regeln, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Nachdem Sie Vertraulichkeitsbezeichnungen mit den zugehörigen Richtlinien im [Microsoft Purview-Complianceportal](/microsoft-365/compliance/go-to-the-securitycompliance-center) konfiguriert haben, können diese Bezeichnungen auf Teams in Ihrer Organisation angewendet werden.

Vertraulichkeitsbezeichnungen werden derzeit in Kursteams für Kunden, die Teams Education-SKUs verwenden, nicht unterstützt. Weitere Informationen zur Lizenzierung finden Sie in der [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>Was ist der Unterschied zwischen Vertraulichkeitsbezeichnungen und Teams-Klassifizierung?

Vertraulichkeitsbezeichnungen unterscheiden sich von der Teams-Klassifizierung, auch bekannt als Azure AD-Gruppenklassifizierung. Klassifizierungen sind Textzeichenfolgen, die einer Microsoft 365-Gruppe zugeordnet werden können, denen jedoch keine tatsächlichen Richtlinien zugeordnet sind. Sie verwenden die Klassifizierung als Metadaten und müssen dann andere Methoden wie interne Tools und Skripts verwenden, um Richtlinien zu erzwingen.

Der Vorteil der Verwendung von Vertraulichkeitsbezeichnungen besteht darin, dass ihre Richtlinien automatisch End-to-End durch eine Kombination aus der Microsoft 365-Gruppen Plattform, der Microsoft Purview-Complianceportal und Teams-Diensten erzwungen werden. Vertraulichkeitsbezeichnungen bieten leistungsstarke Infrastrukturunterstützung, um die vertraulichen Daten Ihrer Organisation zu schützen und die Einhaltung Ihrer internen Richtlinien oder Vorschriften sicherzustellen.

Wenn Sie derzeit die Teams-Klassifizierung verwenden, finden Sie in der folgenden Dokumentation weitere Informationen und Anweisungen zum Konvertieren dieser Werte in Vertraulichkeitsbezeichnungen: [Klassische Azure AD-Gruppenklassifizierung](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Beispielszenarien für Vertraulichkeitsbezeichnungen

Beispielszenarien für die Verwendung von Vertraulichkeitsbezeichnungen mit Teams in Ihrer Organisation sind:

- [Festlegen der Datenschutzstufe (öffentlich oder privat) für Teams](#set-the-privacy-level-for-teams)
- [Steuern des Gastzugriffs auf Teams](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Festlegen der Datenschutzstufe für Teams

Sie können eine Vertraulichkeitsbezeichnung erstellen und konfigurieren, mit der Benutzer, wenn sie während der Teamerstellung angewendet werden, Teams mit einer bestimmten Datenschutzeinstellung (öffentlich oder privat) erstellen können.

Sie erstellen und veröffentlichen z. B. eine Vertraulichkeitsbezeichnung mit dem Namen "Vertraulich", für die die Datenschutzoption "Bezeichnung" als **"Privat**" konfiguriert ist. Daher muss jedes Team, das mit dieser Bezeichnung erstellt wurde, ein privates Team sein. 

Wenn ein Benutzer ein neues Team erstellt und die Bezeichnung **"Vertraulich** " auswählt, ist die einzige Datenschutzoption, die dem Benutzer zur Verfügung steht, **"Privat**". Andere Datenschutzoptionen wie "Öffentlich" und "Organisationsweit" stehen dem Benutzer nicht zur Auswahl:

![Screenshot der Vertraulichkeitsbezeichnung "Vertraulich".](media/sensitivity-labels-confidential-example.png)

Ebenso erstellen und veröffentlichen Sie eine Vertraulichkeitsbezeichnung mit dem Namen "Allgemein", für die die Datenschutzoption "Bezeichnung" als **öffentlich** konfiguriert ist. Wenn ein Benutzer ein neues Team erstellt, kann er nur öffentliche oder organisationsweite Teams erstellen, wenn er diese Bezeichnung auswählt:

![Screenshot der allgemeinen Vertraulichkeitsbezeichnung.](media/sensitivity-labels-general-example.png)

Wenn das Team erstellt wird, ist die Vertraulichkeitsbezeichnung für Benutzer in der oberen rechten Ecke der Kanäle im Team sichtbar. 

![Screenshot der Vertraulichkeitsbezeichnung im Teamkanal.](media/sensitivity-labels-channel.png)

Ein Teambesitzer kann die Vertraulichkeitsbezeichnung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team wechselt und dann auf **"Team bearbeiten"** klickt.

![Screenshot der Vertraulichkeitsbezeichnung in Teameigenschaften.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Steuern des Gastzugriffs auf Teams

Sie können Vertraulichkeitsbezeichnungen verwenden, um den Gastzugriff auf Ihre Teams zu steuern. Teams, die mit einer Bezeichnung erstellt wurden, die keinen Gastzugriff zulässt, sind nur für Benutzer in Ihrer Organisation verfügbar. Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams Admin Center

Sie können Vertraulichkeitsbezeichnungen anwenden, wenn Sie ein Team im Microsoft Teams Admin Center erstellen oder bearbeiten. Vertraulichkeitsbezeichnungen sind auch in Teameigenschaften und in der Spalte **"Klassifizierung"** auf der Seite **"Teams verwalten** " im Microsoft Teams Admin Center sichtbar.

## <a name="limitations"></a>Einschränkungen

Beachten Sie vor der Verwendung von Vertraulichkeitsbezeichnungen für Teams die folgenden Einschränkungen:

- **Vertraulichkeitsbezeichnungen werden von Teams Graph-APIs und PowerShell-Cmdlets nicht unterstützt.**
    
    Benutzer können keine Vertraulichkeitsbezeichnungen angeben, während Sie Teams direkt über Teams Graph-APIs oder Teams PowerShell-Cmdlets erstellen. Moderne Gruppendiagramm-APIs und PowerShell-Cmdlets ermöglichen jedoch das Erstellen von Gruppen mit Vertraulichkeitsbezeichnungen. Dies bedeutet, dass Sie mithilfe dieser Methoden Gruppen mit Vertraulichkeitsbezeichnungen erstellen und diese Gruppen dann in Teams konvertieren können.

- **Unterstützung für private Kanäle**
    
    Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeitsbezeichnung, die auf ein Team angewendet wurde. Dieselbe Bezeichnung wird automatisch auf die SharePoint-Websitesammlung für den privaten Kanal angewendet.
    
    Wenn ein Benutzer jedoch die Vertraulichkeitsbezeichnung auf einer SharePoint-Website für einen privaten Kanal direkt ändert, wird diese Bezeichnungsänderung nicht im Teams-Client widergespiegelt. In diesem Szenario sehen Benutzer weiterhin die ursprüngliche Vertraulichkeitsbezeichnung, die auf das Team im privaten Kanalheader angewendet wurde.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen für Teams

Verwenden Sie die Anweisungen aus der Microsoft Purview-Dokumentation, um Vertraulichkeitsbezeichnungen für Teams zu erstellen und zu konfigurieren: 

- [Verwenden Sie Vertraulichkeitsbezeichnungen, um Inhalte in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites zu schützen](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
