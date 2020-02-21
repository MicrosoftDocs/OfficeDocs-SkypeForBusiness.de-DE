---
title: Aufbewahrungsrichtlinien in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Informieren Sie sich über Aufbewahrungsrichtlinien, und erfahren Sie, wie Sie in Teams erstellt und verwaltet werden.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160749"
---
# <a name="retention-policies-in-microsoft-teams"></a>Aufbewahrungsrichtlinien in Microsoft Teams

Aufbewahrungsrichtlinien helfen Ihnen, die Informationen in Ihrer Organisation effektiver zu verwalten. Verwenden Sie Aufbewahrungsrichtlinien, um Daten zu speichern, die erforderlich sind, um die internen Richtlinien, Branchenrichtlinien oder rechtlichen Anforderungen Ihrer Organisation zu erfüllen, und um Daten zu löschen, die als eine Haftung angesehen werden, die Sie nicht mehr behalten müssen, oder die keinen rechtlichen oder geschäftlichen Wert haben.

Standardmäßig werden die Daten für Teams-Chat, Kanal und Dateien für immer aufbewahrt. Als Administrator können Sie die Aufbewahrungsrichtlinien für Teams für Chats und Kanal Nachrichten einrichten und proaktiv entscheiden, ob Sie die Daten beibehalten, löschen oder für einen bestimmten Zeitraum beibehalten und dann löschen möchten.

Sie erstellen und verwalten Aufbewahrungsrichtlinien für Teams und andere Arbeitslasten im [Office 365 Security & Compliance Center](https://protection.office.com/) oder mithilfe der PowerShell-Cmdlets für Security & Compliance Center. Sie können eine Aufbewahrungsrichtlinie für Teams auf Ihre gesamte Organisation oder bestimmte Benutzer und Teams anwenden.

> [!NOTE]
> Wir unterstützen noch keine Konfiguration für die Aufbewahrung privater Kanal Nachrichten. Die Aufbewahrung von Dateien, die in privaten Kanälen freigegeben sind, wird unterstützt.

Weitere Informationen zu Aufbewahrungsrichtlinien für Office 365 finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="what-are-retention-policies-for-teams"></a>Was sind Aufbewahrungsrichtlinien für Teams?

Wenn Sie eine Aufbewahrungsrichtlinie für Teams oder eine andere Arbeitsauslastung einrichten, können Sie diese wie folgt einrichten:

- **Daten beibehalten**: Verwenden Sie eine Aufbewahrungsrichtlinie, um sicherzustellen, dass Ihre Daten für eine bestimmte Zeitdauer aufbewahrt werden, unabhängig davon, was in der Benutzer-APP geschieht. Daten werden aus Kompatibilitätsgründen aufbewahrt und für eDiscovery bis zum Ablauf des Aufbewahrungszeitraums zur Verfügung gestellt, nach dem Ihre Richtlinie angibt, ob Sie nichts tun oder die Daten löschen möchten. Wenn Sie beispielsweise eine Aufbewahrungsrichtlinie für Teams erstellen, um Kanal Nachrichten sieben Jahre lang beizubehalten, werden die Nachrichten 7 Jahre lang für eDiscovery aufbewahrt, auch wenn Benutzer Ihre Nachrichten in Teams löschen.
- **Löschen von Daten**: Verwenden Sie eine Aufbewahrungsrichtlinie, um Daten zu löschen, um sicherzustellen, dass es sich nicht um eine Haftung für Ihre Organisation handelt. Wenn Sie mit einer Aufbewahrungsrichtlinie für Teams Daten löschen, wird Sie endgültig aus allen Speicherorten des Teams-Diensts gelöscht.

Mit Aufbewahrungsrichtlinien für Teams haben Sie folgende Möglichkeiten:

- Halten Sie Teams-Chats und/oder Kanal Nachrichten für eine bestimmte Dauer fest, und führen Sie dann nichts aus.
- Halten Sie Teams-Chats und/oder Kanal Nachrichten für eine bestimmte Dauer fest, und löschen Sie die Daten.
- Löschen Sie Teams-Chats und/oder Kanal Nachrichten nach einer bestimmten Dauer.

> [!NOTE]
> Beachten Sie, dass Dateien, die Benutzer in privaten Chats freigeben, in Teams im OneDrive for Business-Konto des Benutzers gespeichert sind, der die Datei freigegeben hat. Und Dateien, die Teammitglieder in eine Kanal Unterhaltung hochladen, werden auf der SharePoint-Website des Teams gespeichert. Um Dateien in Teams beizubehalten oder zu löschen, erstellen Sie daher Aufbewahrungsrichtlinien, die für OneDrive for Business und SharePoint Online gelten.

Wenn Daten einer Aufbewahrungsrichtlinie unterliegen, können Benutzer weiterhin daran arbeiten, da die Daten an Ihrem ursprünglichen Speicherort aufbewahrt werden. Wenn ein Benutzerdaten bearbeitet oder löscht, die der Richtlinie unterliegen, wird eine Kopie an einem sicheren Ort gespeichert, an dem Sie aufbewahrt wird, während die Richtlinie gültig ist.

Die Mindestanforderungen für die Lizenzierung für Aufbewahrungsrichtlinien sind Office 365 E3. Weitere Informationen zur Lizenzierung finden Sie unter [Office 365-Lizenzierung für Teams](Office-365-licensing.md).

## <a name="how-teams-retention-policies-work"></a>Funktionsweise von Teams-Aufbewahrungsrichtlinien

Teams-Chats werden in einem versteckten SubstrateHolds-Ordner im Postfach jedes Benutzers im Chat gespeichert, und Teams-Kanal Nachrichten werden in einem ausgeblendeten SubstratesHolds-Ordner im Gruppenpostfach für ein Team gespeichert. Teams verwendet einen Azure-powered-Chatdienst, der auch diese Daten speichert, und Standardmäßig speichert dieser Dienst die Daten für immer. Bei der Aufbewahrungsrichtlinie für Teams werden die Daten beim Löschen von Daten dauerhaft sowohl aus den Exchange-Postfächern als auch aus dem zugrunde liegenden Chatdienst gelöscht.

Wenn Sie eine Aufbewahrungsrichtlinie auf Teams-Chats und Kanal Nachrichten anwenden, gehen Sie folgendermaßen vor:

- Wenn eine Chat-oder Kanal Nachricht während des Aufbewahrungszeitraums von einem Benutzer bearbeitet oder gelöscht wird, wird die Nachricht (sofern Sie bearbeitet wurde) kopiert oder verschoben (falls Sie gelöscht wurde) in den SubstrateHolds-Ordner und dort gespeichert, bis der Aufbewahrungszeitraum abläuft. Wenn die Richtlinie zum Löschen von Daten nach Ablauf des Aufbewahrungszeitraums konfiguriert ist, werden Nachrichten an dem Tag, an dem der Aufbewahrungszeitraum abläuft, endgültig gelöscht.
- Wenn eine Chat-oder Kanal Nachricht während des Aufbewahrungszeitraums nicht von einem Benutzer gelöscht wird, wird die Nachricht innerhalb eines Tages nach Ablauf des Aufbewahrungszeitraums in den SubstrateHolds-Ordner verschoben. Wenn die Richtlinie zum Löschen von Daten nach Ablauf des Aufbewahrungszeitraums konfiguriert ist, wird die Nachricht einen Tag nach dem Verschieben in den Ordner endgültig gelöscht.

> [!NOTE]
> Derselbe Flow funktioniert für Skype for Business Online und für Teams-Interop-Chats. Wenn ein Skype for Business Online-Chat in Teams eingeht, wird er in einem Teamchat-Thread zu einer Nachricht und wird in das entsprechende Postfach aufgenommen. In den Teams-Aufbewahrungsrichtlinien werden diese Nachrichten aus dem teamthread gelöscht. Wenn das Unterhaltungsprotokoll jedoch für Skype for Business Online und von der Skype for Business Online-Clientseite aktiviert ist, die in einem Postfach gespeichert werden, werden diese Chat-Daten nicht von einer Aufbewahrungsrichtlinie für Teams verarbeitet.

Aufbewahrungsrichtlinien in Teams basieren auf dem Datum, an dem die Chat-oder Kanal Nachrichten erstellt wurden und rückwirkend sind. Anders ausgedrückt: Wenn Sie eine Aufbewahrungsrichtlinie zum Löschen von Daten erstellen, die älter als 90 Tage sind, werden die vor mehr als 90 Tagen erstellten Team Daten gelöscht.

Es ist möglich, dass eine auf SharePoint Online oder OneDrive for Business angewendete Aufbewahrungsrichtlinie eine Datei löschen kann, auf die in einem Teamchat oder in einer Kanal Nachricht verwiesen wird, bevor diese Nachrichten gelöscht werden. In diesem Szenario wird die Datei weiterhin in der Team Nachricht angezeigt, aber wenn Benutzer auf die Datei klicken, wird die Fehlermeldung "Datei nicht gefunden" angezeigt. Dies kann auch auftreten, wenn eine Richtlinie nicht vorhanden ist, wenn jemand eine Datei manuell aus SharePoint Online oder OneDrive for Business löscht.

### <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

Im folgenden sind einige Überlegungen und Einschränkungen zu beachten, die bei der Arbeit mit den Aufbewahrungsrichtlinien für Teams beachtet werden:

- Für Teams ist eine Aufbewahrungsrichtlinie erforderlich, die von anderen Arbeitsauslastungen getrennt ist. Anders ausgedrückt: Sie müssen bestimmte Aufbewahrungsrichtlinien für Teams-Chats und/oder Kanal Nachrichten erstellen. Aus diesem Grund können Sie keine Teams in organisationsweite Aufbewahrungsrichtlinien einbeziehen.

- Private Kanal Nachrichten werden nicht unterstützt. Zu diesem Zeitpunkt gelten Aufbewahrungsrichtlinien für Teams nur für Standardkanal Nachrichten.

- Teams unterstützt keine erweiterten Aufbewahrungseinstellungen, beispielsweise die Möglichkeit, eine Richtlinie auf Inhalte anzuwenden, die Stichwörter oder vertrauliche Informationen enthalten. Derzeit gelten Aufbewahrungsrichtlinien in Teams für alle Chat-und/oder Kanal Nachrichteninhalte.

- Für Teams kann es bis zu drei Tage dauern, bis abgelaufene Nachrichten bereinigt wurden. Eine Aufbewahrungsrichtlinie für Teams löscht Chat-und Kanal Nachrichten, wenn der Aufbewahrungszeitraum abgelaufen ist. Es kann jedoch bis zu drei Tage dauern, bis diese Nachrichten bereinigt und endgültig gelöscht wurden. Darüber hinaus können Chat-und Kanal Nachrichten mit eDiscovery-Tools zwischen der Zeit nach Ablauf des Aufbewahrungszeitraums und nach dem endgültigen Löschen von Nachrichten durchsucht werden.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Mehrere Aufbewahrungsrichtlinien und die Grundsätze der Aufbewahrung

Wenn Sie mehrere Teams-Aufbewahrungsrichtlinien mit unterschiedlichen Dauer einrichten, gelten die [Grundsätze der Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) . Im folgenden finden Sie eine Übersicht über das, was Vorrang hat:

- Beibehaltung gewinnt immer über Löschung
- Der längste Aufbewahrungszeitraum gewinnt immer
- Explizite Inklusion gewinnt über implizite Inklusion in Bezug auf Speicherorte
- Kürzester Lösch Zeitraum gewinnt

## <a name="when-to-use-retention-policies-for-teams"></a>Verwendung von Aufbewahrungsrichtlinien für Teams

In vielen Fällen sehen Organisationen private Chat-Daten eher als eine Haftung als Kanal Nachrichten an, die in der Regel mehr projektbezogene Unterhaltungen sind.

Sie können separate Aufbewahrungsrichtlinien für private Chats (1:1 oder 1: viele Chats) und Kanal Nachrichten einrichten. Sie können auch eindeutige Richtlinien konfigurieren, die für bestimmte Benutzer oder Teams in Ihrer Organisation gelten. Für Teams-Chats können Sie auswählen, auf welche Benutzer die Richtlinie angewendet werden soll. Für Teams-Kanal Nachrichten können Sie auswählen, für welche Teams die Richtlinie gelten soll.

So können Sie beispielsweise für Kanal Nachrichten eine einjährige Löschrichtlinie auf bestimmte Teams in Ihrer Organisation anwenden und auf alle anderen Teams eine Löschrichtlinie für drei Jahre anwenden.

## <a name="manage-retention-policies-for-teams"></a>Verwalten von Aufbewahrungsrichtlinien für Teams

### <a name="using-the-security--compliance-center"></a>Verwenden des Security & Compliance Centers

#### <a name="create-a-retention-policy"></a>Erstellen einer Aufbewahrungsrichtlinie

Gehen Sie wie folgt vor, um eine Aufbewahrungsrichtlinie für Teams-Chats und Kanal Nachrichten zu erstellen:

1. Wechseln Sie in der linken Navigationsleiste des Security & Compliance Centers zu **Information Governance** > -**Aufbewahrung**.
2. Wählen Sie **Erstellen**aus.
3. Geben Sie auf der Seite **Richtlinie benennen** einen Namen und eine Beschreibung für die Richtlinie ein, und klicken Sie dann auf **weiter**.
4. Geben Sie auf der Seite **Einstellungen** an, ob Sie die Daten beibehalten, die Aufbewahrungsdauer oder beides löschen möchten, und klicken Sie dann auf **weiter**.
5. Führen Sie auf der Seite **"Speicherorte auswählen** " die folgenden Schritte aus, und klicken Sie dann auf **weiter**:

    - Um die Richtlinie auf Kanal Nachrichten anzuwenden, aktivieren Sie die **Kanal Nachrichten von Teams**.  Wenn Sie die Richtlinie auf bestimmte Teams in Ihrer Organisation anwenden möchten, wählen Sie **Teams**auswählen aus, und wählen Sie dann die gewünschten Teams aus.
    - Wenn Sie die Richtlinie auf Chats anwenden möchten, aktivieren Sie **Teams-Chats**. Wenn Sie die Richtlinie auf bestimmte Benutzer in Ihrer Organisation anwenden möchten, wählen Sie **Benutzer**auswählen aus, und wählen Sie dann die gewünschten Benutzer aus.
      > [!NOTE]
      > Wenn Sie Teams- **Kanal Nachrichten** und/oder **Teams-Chats**aktivieren, werden alle anderen Standorte automatisch deaktiviert. Eine Aufbewahrungsrichtlinie für Teams kann nur Teams-Standorte umfassen.

        ![Screenshot der Optionen "Teams Kanal Nachrichten" und "Teams Chats" auf der Seite "Orte auswählen"](media/retention-policies-create.png)

      > [!IMPORTANT]
      > Teams-Chats und Kanal Nachrichten sind nicht von Aufbewahrungsrichtlinien betroffen, die auf Benutzer-oder Gruppen Postfächer in den **Exchange-e-Mail-** oder **Office 365-Gruppen** Speicherorten angewendet werden. Obwohl Teams-Chats und Kanal Nachrichten in Exchange gespeichert werden, sind Sie nur von Aufbewahrungsrichtlinien betroffen, die auf die Teams-Standorte angewendet werden.

6. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann, wenn Sie fertig sind, **Diese Richtlinie erstellen**aus.

#### <a name="edit-a-retention-policy"></a>Bearbeiten einer Aufbewahrungsrichtlinie

Gehen Sie wie folgt vor, um eine Aufbewahrungsrichtlinie für Teams zu bearbeiten:

1. Wechseln Sie in der linken Navigationsleiste des Security & Compliance Centers zu **Information Governance** > -**Aufbewahrung**.
2. Aktivieren Sie in der Liste der Aufbewahrungsrichtlinien das Kontrollkästchen neben der Aufbewahrungsrichtlinie, die Sie bearbeiten möchten.
3. Wählen Sie neben dem, was Sie bearbeiten möchten, die Option **Bearbeiten** aus, nehmen Sie die gewünschten Änderungen vor, klicken Sie auf **Speichern**und dann auf **Schließen**.

    ![Screenshot der Optionen "Teams Kanal Nachrichten" und "Teams Chats" auf der Seite "Orte auswählen"](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>Löschen einer Aufbewahrungsrichtlinie

Gehen Sie wie folgt vor, um eine Aufbewahrungsrichtlinie für Teams zu löschen:

1. Wechseln Sie in der linken Navigationsleiste des Security & Compliance Centers zu **Information Governance** > -**Aufbewahrung**.
2. Aktivieren Sie in der Liste der Aufbewahrungsrichtlinien das Kontrollkästchen neben der Aufbewahrungsrichtlinie, die Sie löschen möchten.
3. Wählen Sie **Richtlinie löschen**aus.

### <a name="using-powershell"></a>Verwenden von PowerShell

Verwenden Sie die folgenden Cmdlets, um die Aufbewahrungsrichtlinien für Teams mithilfe von PowerShell zu erstellen und zu verwalten.

|Richtlinie|Regel|
|---|---|
|[Neu – TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Neu – TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Satz-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Satz-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Bekannte Probleme

Im folgenden werden bekannte Probleme bei Aufbewahrungsrichtlinien in Teams aufgeführt, die nachverfolgt und untersucht werden.

- Unter **"Teams auswählen"** in der Zeile " **Channel-Nachrichten für Teams** " werden möglicherweise Office 365-Gruppen angezeigt, die nicht auch Teams sind. Dies wird in Zukunft behoben.

- Unter **Benutzer** in der Zeile **teamchats** -Standort auswählen werden möglicherweise Gäste und nicht-Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sind für Gäste nicht vorgesehen, und wir arbeiten daran, diese aus der Liste zu entfernen.

- Exchange-Lebenszyklus-Assistent (ELC) wird täglich ausgeführt, hat aber eine SLA von 7 Tagen. Daher ist es möglich, dass diese Elemente für bis zu 67 Tage beibehalten werden, wenn Sie über eine Aufbewahrungsrichtlinie für Teams verfügen, um Elemente zu löschen, die älter als 60 Tage sind. Dies ist keine neue Situation – Sie folgt dem Exchange-Modell. In den meisten Fällen gibt es natürlich keine Verzögerung.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
