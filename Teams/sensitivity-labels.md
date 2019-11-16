---
title: Vertraulichkeits Bezeichnungen für Microsoft Teams
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Vertraulichkeits Beschriftungen in Microsoft Teams definieren und verwenden.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653581"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Vertraulichkeits Bezeichnungen für Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Mit [Vertraulichkeits Beschriftungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) können Teams-Administratoren den Zugriff auf vertrauliche organisatorische Inhalte regulieren, die während der Zusammenarbeit in Teams erstellt wurden. Sie können Vertraulichkeits Bezeichnungen und die zugehörigen Richtlinien im [Security #a0 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)definieren. Diese Bezeichnungen und Richtlinien werden automatisch auf Teams in Ihrer Organisation angewendet.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Was ist der Unterschied zwischen Vertraulichkeits Beschriftungen und Klassifikations Etiketten für Teams?

Vertraulichkeits Beschriftungen unterscheiden sich von Klassifizierungs Beschriftungen, die Sie mit PowerShell erstellen müssen. Klassifikations Beschriftungen sind Textzeichenfolgen, die einer Gruppe zugeordnet werden können, denen jedoch keine eigentlichen Richtlinien zugeordnet sind. Sie verwenden Klassifizierungs Beschriftungen als Metadaten, um Richtlinien mithilfe interner Tools und Skripts manuell durchzusetzen.

Auf der anderen Seite werden die Vertraulichkeits Beschriftungen und ihre Richtlinien durch eine Kombination aus den Gruppen Plattform, Security #a0 Compliance Center und Teams Services automatisch durchgesetzt. Vertraulichkeits Beschriftungen bieten leistungsstarke Infrastrukturunterstützung zum Sichern vertraulicher Daten Ihrer Organisation.  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a>Erstellen und Veröffentlichen von Vertraulichkeits Beschriftungen für Teams

Informationen zum Aktivieren, erstellen und Veröffentlichen von Vertraulichkeits Bezeichnungen für Teams finden Sie unter [Verwenden von Vertraulichkeits Bezeichnungen in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="using-sensitivity-labels-with-teams"></a>Verwenden von Vertraulichkeits Beschriftungen in Teams

Im folgenden finden Sie einige Beispielszenarien für die Verwendung von Vertraulichkeits Beschriftungen in Teams in Ihrer Organisation.

### <a name="privacy-setting-of-teams"></a>Datenschutzeinstellungen für Teams

Sie können eine Vertraulichkeits Beschriftung erstellen, die den Benutzern beim Anwenden während der Teamerstellung ermöglicht, Teams mit einer bestimmten Einstellung für Privatsphäre (öffentlich oder privat) zu erstellen.

Beispielsweise erstellen Sie im Security #a0 Compliance Center ein Etikett mit dem Namen "vertraulich", und Sie konfigurieren Teams so, dass jedes Team, das mit diesem Label erstellt wurde, ein privates Team sein muss. Wenn ein Benutzer ein neues Team erstellt und das **vertrauliche** Etikett auswählt, ist die einzige Datenschutzoption, die dem Benutzer zur Verfügung steht, **Privat**. Andere Datenschutzoptionen wie Public und org-Wide sind für den Benutzer deaktiviert.

![Screenshot der vertraulichen Vertraulichkeits Kennzeichnung](media/sensitivity-labels-confidential-example.png)

Auch wenn der Benutzer beim Erstellen eines neuen Teams " **Allgemein** " auswählt, kann er nur öffentliche oder organisationsweite Teams erstellen.

![Screenshot der allgemeinen Vertraulichkeits Beschriftung](media/sensitivity-labels-general-example.png)

Wenn das Team erstellt wird, wird die Vertraulichkeits Bezeichnung in der oberen rechten Ecke der Kanäle im Team angezeigt.

![Screenshot der Vertraulichkeits Beschriftung im Team Kanal](media/sensitivity-labels-channel.png)

Ein Teambesitzer kann die Vertraulichkeits Beschriftung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team wechselt und dann auf **Team bearbeiten**klickt.

![Screenshot der Vertraulichkeits Beschriftung im Team Kanal](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Gastzugriff auf Teams

Sie können angeben, ob ein Team, das mit einer bestimmten Bezeichnung erstellt wurde, Gastzugriff ermöglicht. Teams, die mit einer Beschriftung erstellt wurden, die keinen Gastzugriff zulässt, stehen nur Benutzern in Ihrer Organisation zur Verfügung. Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.

## <a name="known-issues"></a>Bekannte Probleme

**Unterstützung für Vertraulichkeits Beschriftungen im Microsoft Teams Admin Center**

Derzeit werden Vertraulichkeits Beschriftungen im Microsoft Teams Admin Center nicht unterstützt. Wenn Sie Vertraulichkeits Beschriftungen verwenden, können Sie beim Erstellen oder Bearbeiten eines Teams keine Vertraulichkeits Beschriftungen einstellen. Vertraulichkeits Beschriftungen sind auch in den teameigenschaften nicht sichtbar und werden in der Spalte **Klassifizierung** des Microsoft Teams admin Centers nicht angezeigt.

**Unterstützung für Vertraulichkeits Beschriftungen in Teams-Diagramm-APIs, PowerShell-Cmdlets und-Vorlagen**

Derzeit können Benutzer keine Vertraulichkeits Bezeichnungen für Teams anwenden, die direkt über Diagramm-APIs, PowerShell-Cmdlets und Vorlagen erstellt wurden.

**Bearbeiten von Vertraulichkeits Beschriftungen direkt in einer SharePoint-Websitesammlung für private Kanäle**

Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeits Bezeichnung, die in einem Team angewendet wurde. Darüber hinaus wird dieselbe Bezeichnung automatisch für die SharePoint-Websitesammlung für den privaten Kanal übernommen.

Wenn ein Benutzer die Vertraulichkeits Beschriftung auf einer SharePoint-Websitesammlung für einen privaten Kanal direkt aktualisiert, wird diese Bezeichnung nicht im Team-Client aktualisiert. In diesem Szenario wird den Benutzern weiterhin die auf ein Team angewendete Vertraulichkeits Bezeichnung in der Kopfzeile privater Kanal angezeigt.

**Ausbreitungs Zeiten für Änderungen, die auf Vertraulichkeits Beschriftungen außerhalb der Teams-App angewendet werden**

Änderungen an Vertraulichkeits Beschriftungen außerhalb der Teams-App können bis zu 24 Stunden dauern, bis Sie in der Teams-App wiedergegeben werden. Dies gilt für alle Änderungen, die vorgenommen wurden, um Bezeichnungen für einen Mandanten zu aktivieren oder zu deaktivieren, Änderungen an Etikettennamen, Einstellungen und Richtlinien.

Darüber hinaus kann es bis zu 24 Stunden dauern, bis Änderungen an einer Bezeichnung, die direkt an eine Gruppe oder SharePoint-Websitesammlung, die das Team zurückgibt, an die Teams-App weitergegeben werden.