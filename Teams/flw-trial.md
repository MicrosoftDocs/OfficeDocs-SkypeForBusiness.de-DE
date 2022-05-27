---
title: Verwalten der Frontline-Testversion in Teams
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie eine 90-tägige Teams für Mitarbeiter in Service und Produktion für Ihre Organisation einrichten.
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758296"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Verwalten der Frontline-Testversion in Teams

> [!NOTE]
> Diese Testversion wird in Kürze verfügbar sein. Sie können überprüfen, ob dies für Ihre Organisation verfügbar ist, indem Sie im [Nachrichtencenter](https://go.microsoft.com/fwlink/p/?linkid=2070717) in Ihrem Microsoft 365 Admin Center nach einer Nachricht suchen.

Mit der Microsoft Teams Frontline-Testversion können Benutzer in Ihrer Organisation, die sich in Teams befinden, eine Teams Erfahrung für ihr gesamtes Frontlineteam initiieren, solange sich die anderen Mitglieder in Azure Active Directory (Azure AD) befinden. Sie können dieses Feature für Benutzer in Ihrer Organisation mithilfe des [PowerShell-Moduls "AllowSelfServicePurchase](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)" deaktivieren.

## <a name="what-services-are-included"></a>Welche Dienste sind enthalten?

Die Testversion enthält alles in der [Microsoft 365 F3-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/f3) mit den folgenden Ausnahmen:

- Die Frontline-Testversion umfasst Exchange Foundation und nicht Exchange Kiosk. Benutzern fehlen aufgrund dieser Änderung möglicherweise andere Teams Funktionen.

## <a name="eligibility"></a>Förderfähigkeit

> [!NOTE]
> Sie können überprüfen, ob Ihre Organisation Teil des Testpiloten ist, indem Sie im [Nachrichtencenter](https://go.microsoft.com/fwlink/p/?linkid=2070717) in Ihrem Microsoft 365 Admin Center nach einer Ankündigung suchen. Ihre Organisation muss Teil des Testpiloten sein, damit Benutzer eine Testversion initiieren oder daran teilnehmen können. Dieses Angebot gilt nicht für GCC-, GCC High-, DoD- oder EDU-Kunden.

Die Frontline-Testversion kann maximal 300 Benutzer pro Testversion aufnehmen.

Benutzer können eine Testversion in Service und Produktion für ihr Team starten, wenn sie:

- Verfügen Sie über eine aktive Lizenz, die ihnen Zugriff auf Teams gewährt.
- Sie haben zuvor noch keine Testversion für Mitarbeiter in Service und Produktion gestartet.

> [!IMPORTANT]
> Wenn der Benutzer, der die Testversion initiiert hat, Ihre Organisation verlässt, bevor die Testversion endet, müssen Sie als Administrator die Testversion überwachen, sich mit dem Team anmelden, um zu sehen, wer von diesen Features profitiert, und entscheiden, welche Benutzer Sie auf eine kostenpflichtige Lizenz aktualisieren müssen.

Benutzer können an einer Testversion von Mitarbeiter in Service und Produktion teilnehmen, wenn sie über eine verwaltete Azure Active Directory Domänen-E-Mail-Adresse verfügen.

Benutzer können teilnehmen, wenn sie zuvor eine Testversion gestartet haben, aber keine weitere Testversion initiieren können.

> [!NOTE]
> Benutzer ohne vorhandenen Zugriff auf Teams können dem Testteam nur zum Zeitpunkt der Teamerstellung hinzugefügt werden. Vorhandene Teams Benutzer können der Testversion noch hinzugefügt werden, nachdem das Team erstellt wurde.

## <a name="set-up-the-trial"></a>Einrichten der Testversion

Berechtigte Benutzer können eine Frontline-Testversion starten, indem sie sich in Teams über die Desktop- oder [Web-App](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks) bei der Aufgaben-App anmelden. Derzeit wird das Starten einer Frontline-Testversion über Mobile nicht unterstützt. Wenn eine Testversion initiiert wird, wird dem gesamten Team automatisch die Lizenz für die Testversion in Service und Produktion zugewiesen. Benutzern mit vorhandenen kostenpflichtigen Lizenzen, die ihnen Zugriff auf Teams gewähren, werden ebenfalls Testlizenzen zugewiesen, behalten jedoch die Funktionalität ihrer vorhandenen Lizenzen während der Testversion bei und behalten ihre vorhandenen kostenpflichtigen Lizenzen nach Ablauf der Testversion bei. Der Benutzer, der die Testversion gestartet hat, erhält während des gesamten Testzeitraums E-Mail-Benachrichtigungen.

## <a name="manage-the-frontline-trials-experience"></a>Verwalten der Testumgebung in Service und Produktion

Administratoren können verhindern, dass Endbenutzer die Frontline-Testversion in ihrer Organisation starten, indem sie das PowerShell-Modul **"AllowSelfServicePurchase** " verwenden. Dies gilt nur für Testlizenzen. [Erfahren Sie, wie Sie das PowerShell-Modul "AllowSelfServicePurchase" verwenden](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Verwalten von Teams für Benutzer, die über die Frontline-Testlizenz verfügen

Sie können Benutzer, die über die Frontline-Testlizenz verfügen, genauso wie Benutzer verwalten, die über eine reguläre kostenpflichtige Lizenz verfügen. Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](/microsoftteams/manage-teams-overview).

### <a name="remove-a-trial-license"></a>Entfernen einer Testlizenz

Sie können die Lizenz für die Frontline-Testversion über PowerShell oder Ihre Microsoft 365 Admin Center entfernen.

[Erfahren Sie, wie Sie mit PowerShell entfernen](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

[Erfahren Sie, wie Sie im Admin Center entfernen](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>Aktualisieren von Benutzern aus der Frontline-Testversion

Benutzer können sich an Sie wenden, um Lizenzen zu beantragen, wenn die Testversion endet. Sie benötigen Administratorrechte, um Ihre Benutzer zu aktualisieren.

### <a name="when-to-upgrade"></a>Zeitpunkt des Upgrades

Gegen Ende der 90-tägigen Testversion müssen Sie sich mit Ihren Benutzern erkundigen, wer mit einer kostenpflichtigen Lizenz fortfahren muss. Stellen Sie sicher, dass Sie dies tun, bevor das Frontline-Testabonnement abläuft, um Unterbrechungen der Benutzererfahrungen zu vermeiden.

> [!IMPORTANT]
> Wenn die Frontline-Testlizenz endet und einem Benutzer nicht sofort eine Lizenz zugewiesen wird, die Teams enthält, verliert er den Zugriff auf Teams. Nach 30 Tagen werden ihre Daten (Dateien, Nachrichten und mehr) gelöscht. Der Benutzer ist weiterhin in Azure Active Directory vorhanden. Wenn dem Benutzer eine neue Lizenz zugewiesen wird, um Teams Funktionalität innerhalb des Zeitraums von 30 Tagen zu aktivieren, sind alle inhalte in Teams weiterhin vorhanden.

### <a name="choose-an-upgrade-path"></a>Auswählen eines Upgradepfads

> [!TIP]
> Die Frontline-Testversion basiert auf der [Microsoft 365 F3 Lizenz](https://www.microsoft.com/microsoft-365/enterprise/f3).

Je nach den Abonnements, über die Ihre Organisation derzeit verfügt, gibt es drei Möglichkeiten zum Upgrade von einer Frontline-Testversion auf eine kostenpflichtige Lizenz:

- **Upgrade eines vorhandenen Microsoft 365-Abonnements.** Verwenden Sie diese Option, wenn Ihre Organisation Abonnements für andere Office-Produkte hat, die Microsoft Teams nicht enthalten. Weitere Informationen finden Sie unter [Upgrade auf einen anderen Plan](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). Um aktive Benutzer für ein vorhandenes Abonnement anzuzeigen, wechseln Sie im Microsoft 365 Admin Center zu **Benutzer >** [Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822).

- **Hinzufügen von Benutzern zu einem vorhandenen Microsoft 365-Abonnement.** Verwenden Sie diese Option, wenn Ihre Organisation nicht über genügend bezahlte Teams Lizenzen verfügt, um Ihr Frontlineteam abzudecken. Weitere Informationen finden Sie unter [Kaufen oder Entfernen von Lizenzen](/microsoft-365/commerce/licenses/buy-licenses). Informationen zum Hinzufügen von Benutzern zu einem vorhandenen Abonnement, das über genügend verfügbare Lizenzen verfügt, finden Sie unter [Verschieben von Benutzern in ein anderes Abonnement](/microsoft-365/commerce/subscriptions/move-users-different-subscription). Um aktive Benutzer für ein vorhandenes Abonnement anzuzeigen, wechseln Sie im Microsoft 365 Admin Center zu **Benutzer >** [Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822).

- **Kaufen eines neuen Microsoft 365-Abonnements.** Verwenden Sie diese Option, wenn Ihre Organisation über keine Abonnements für Office Produkte verfügt oder wenn Ihre Organisation ein Abonnement kaufen möchte, das sich von ihrem vorhandenen Abonnement unterscheidet, um Frontline-Benutzer abzudecken. Weitere Informationen finden Sie [unter Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline).

Wenn Sie nicht sicher sind, auf welches Microsoft 365 Abonnement aktualisiert werden soll, lesen Sie [Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline). Wenn Sie zusätzliche Hilfe bei der Auswahl eines Abonnements benötigen, oder wenn Ihre Organisation mehr als 300 Lizenzen benötigt, wenden Sie sich an Ihren [Microsoft-Partner](https://www.microsoft.com/solution-providers/home) oder Microsoft-Kundenbetreuer.

### <a name="assign-paid-licenses"></a>Zuweisen kostenpflichtiger Lizenzen

Informationen zum Zuweisen ihrer neu erworbenen Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users).  

Nachdem Sie die neuen Lizenzen zugewiesen haben, heben Sie die Zuweisung der Microsoft Teams Exploratory-Lizenzen auf. Weitere Informationen finden Sie unter [Aufheben der Zuweisung von Lizenzen für Benutzer](/microsoft-365/admin/manage/remove-licenses-from-users).

## <a name="faq"></a>Häufig gestellte Fragen

**Wie lange dauert die Testversion?** <br>
Die Testversion in Service und Produktion dauert 90 Tage.

**Was sollten Administratoren am Ende der 90-tägigen Testversion von Frontline tun?** <br>
Am Ende der 90-tägigen Testversion müssen Sie sich mit Ihren Benutzern erkundigen, wer mit einer kostenpflichtigen Lizenz fortfahren muss. Anschließend müssen Sie [die Benutzer aktualisieren](#upgrade-users-from-frontline-trial).

**Was geschieht, wenn der Benutzer, der die Testversion gestartet hat, Ihre Organisation verlässt?** <br>
Sie als Administrator müssen die Testversion für den Rest des 90-Tage-Zeitraums überwachen und ein Upgrade auf kostenpflichtige Lizenzen für Benutzer durchführen, die sie benötigen, wenn die Testversion endet.

**Was ist die Datenaufbewahrungsrichtlinie?** <br>
Informationen zur Datenaufbewahrung finden Sie in den [Microsoft 365 Abonnementinformationen](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?).

**Was geschieht, wenn ein Benutzer beim Starten der Frontline-Testversion auf einen Fehler stößt?** <br>
Stellen Sie sicher, dass Ihre Organisation, der Benutzer, der die Testversion startet, und die Benutzer, die der Testversion hinzugefügt werden, die [Berechtigungskriterien](#eligibility) erfüllen.