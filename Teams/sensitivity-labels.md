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
description: Erfahren Sie, wie Sie Vertraulichkeitsbeschriftungen verwenden, um Ihre Teams in Microsoft Teams zu schützen.
ms.openlocfilehash: 6929e9c51f35cb4483c81323048b2a1f9ec6243a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875105"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Vertraulichkeitsbezeichnungen für Microsoft Teams

[Vertraulichkeitsbeschriftungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ermöglichen Es Teams-Administratoren, den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regeln, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Nachdem Sie Vertraulichkeitsbeschriftungen mit den zugehörigen Richtlinien im [Microsoft Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)konfiguriert haben, können diese Bezeichnungen auf Teams in Ihrer Organisation angewendet werden.

Vertraulichkeitsbeschriftungen werden derzeit für Kunden mit Teams Education SKUs nicht unterstützt. Weitere Informationen zur Lizenzierung finden Sie in der [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Was ist der Unterschied zwischen Vertraulichkeitsbeschriftungen und Teams-Klassifizierungsbeschriftungen?

Vertraulichkeitsbeschriftungen unterscheiden sich von Klassifizierungsbeschriftungen, die auch als Azure AD-Gruppenklassifizierung bezeichnet werden. Klassifizierungsbeschriftungen sind Textzeichenfolgen, die einer Microsoft 365-Gruppe zugeordnet werden können, ihnen aber keine tatsächlichen Richtlinien zugeordnet sind. Sie verwenden Klassifizierungsbeschriftungen als Metadaten und müssen dann andere Methoden wie interne Tools und Skripts verwenden, um Richtlinien zu erzwingen.

Der Vorteil der Verwendung von Vertraulichkeitsbeschriftungen besteht in der automatischen Erzwingung ihrer Richtlinien durch eine Kombination aus der Microsoft 365-Gruppenplattform, dem Compliance Center und den Teams-Diensten. Vertraulichkeitsbeschriftungen bieten leistungsstarke Infrastrukturunterstützung zum Sichern der vertraulichen Daten Ihrer Organisation und zur Sicherstellung der Einhaltung Ihrer internen Richtlinien oder Vorschriften.

Wenn Sie zurzeit Klassifizierungsbeschriftungen verwenden, finden Sie in der folgenden Dokumentation weitere Informationen und Anweisungen zum Migrieren zu Vertraulichkeitsbeschriftungen: [Klassische Azure AD-Gruppenklassifizierung.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>Beispielszenarien für Vertraulichkeitsbeschriftungen

Beispielszenarien für die Verwendung von Vertraulichkeitsbeschriftungen mit Teams in Ihrer Organisation:

- [Festlegen der Datenschutzstufe (öffentlich oder privat) für Teams](#set-the-privacy-level-for-teams)
- [Steuern des Gastzugriffs auf Teams](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Festlegen der Datenschutzstufe für Teams

Sie können eine Vertraulichkeitsbezeichnung erstellen und konfigurieren, die benutzern das Erstellen von Teams mit einer bestimmten Privaten (öffentlichen oder privaten) Einstellung ermöglicht, wenn sie während der Teamerstellung angewendet wird.

Sie erstellen und veröffentlichen z. B. eine Vertraulichkeitsbezeichnung mit dem Namen "Vertraulich", für die die Option zum Datenschutz der Bezeichnung als **Privat konfiguriert ist.** Daher muss jedes Team, das mit dieser Bezeichnung erstellt wurde, ein privates Team sein. 

Wenn ein Benutzer ein neues Team  erstellt und die Bezeichnung Vertraulich auswählt, ist die einzige Datenschutzoption, die dem Benutzer zur Verfügung steht, **Privat.** Andere Datenschutzoptionen wie "Öffentlich" und "Organisationsweit" stehen dem Benutzer nicht zur Auswahl:

![Screenshot der Vertraulichkeitsbezeichnung "Vertraulich"](media/sensitivity-labels-confidential-example.png)

Ebenso erstellen und veröffentlichen Sie eine Vertraulichkeitsbezeichnung mit dem Namen "Allgemein", für die die Option zum Datenschutz der Bezeichnung als öffentlich **konfiguriert ist.** Wenn ein Benutzer ein neues Team erstellt, kann er nur öffentliche oder organisationsweite Teams erstellen, wenn er diese Bezeichnung auswählt:

![Screenshot der Bezeichnung "Allgemeine Vertraulichkeit"](media/sensitivity-labels-general-example.png)

Wenn das Team erstellt wird, wird die Vertraulichkeitsbeschriftung in der oberen rechten Ecke der Kanäle im Team angezeigt. Beachten Sie, dass bei Verwendung hierarchischer übergeordneter untergeordneter Bezeichnungen wie "Vertraulich\Finanzen" nur die übergeordnete Bezeichnung im Kanalkopf angezeigt wird.


![Screenshot der Vertraulichkeitsbezeichnung im Teamkanal](media/sensitivity-labels-channel.png)

Ein Teambesitzer kann die Vertraulichkeitsbezeichnung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team wechseln und dann auf **Team bearbeiten klickt.**

![Screenshot der Vertraulichkeitsbeschriftung in Teameigenschaften](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Steuern des Gastzugriffs auf Teams

Sie können Vertraulichkeitsbeschriftungen verwenden, um den Gastzugriff auf Ihre Teams zu steuern. Teams, die mit einer Bezeichnung erstellt wurden, die keinen Gastzugriff zu lässt, stehen nur Benutzern in Ihrer Organisation zur Verfügung. Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams Admin Center

Sie können Vertraulichkeitsbeschriftungen anwenden, wenn Sie ein Team im Microsoft Teams Admin Center erstellen oder bearbeiten. 

Vertraulichkeitsbeschriftungen sind auch in Teameigenschaften und in der **Spalte Klassifizierung** auf der Seite **Teams** verwalten im Microsoft Teams Admin Center sichtbar.

## <a name="limitations"></a>Einschränkungen

Beachten Sie vor der Verwendung von Vertraulichkeitsbeschriftungen für Teams die folgenden Einschränkungen:

- **Übergeordnete Bezeichnungsnamen werden für Unteretiketten nicht angezeigt**
    
    Teams unterstützt Unterbezeichnungen, zeigt jedoch nicht den Namen der übergeordneten Bezeichnung an. Beispielsweise wird **"Vertraulich** \\ **alle Mitarbeiter"** als **"Alle Mitarbeiter" angezeigt.**

- **Vertraulichkeitsbeschriftungen werden von Teams Graph-APIs, PowerShell-Cmdlets und Vorlagen nicht unterstützt.**
    
    Benutzer können keine Vertraulichkeitsbeschriftungen auf Teams anwenden, die direkt über Teams Graph-APIs, Teams PowerShell-Cmdlets und Teams-Vorlagen erstellt werden.

- **Unterstützung für private Kanäle**
    
    Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeitsbezeichnung, die auf ein Team angewendet wurde. Dieselbe Bezeichnung wird automatisch auf die SharePoint-Websitesammlung für den privaten Kanal angewendet.
    
    Wenn ein Benutzer jedoch die Vertraulichkeitsbeschriftung auf einer SharePoint-Website für einen privaten Kanal direkt ändert, wird diese Bezeichnungsänderung im Teams-Client nicht wider. In diesem Szenario wird den Benutzern weiterhin die ursprüngliche Vertraulichkeitsbezeichnung angezeigt, die im Kopf des privaten Kanals auf das Team angewendet wurde.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Erstellen und Konfigurieren von Vertraulichkeitsbeschriftungen für Teams

Verwenden Sie die Anweisungen aus der Microsoft 365-Dokumentation, um Vertraulichkeitsbeschriftungen für Teams zu erstellen und zu konfigurieren: 

- [Verwenden Sie Vertraulichkeitsbeschriftungen, um Inhalte in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites zu schützen.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
