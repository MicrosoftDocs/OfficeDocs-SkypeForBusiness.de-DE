---
title: Konfigurieren von Operator Connect
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie Näheres über das Konfigurieren von Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886a9b87154555e75a8f3fbd76002efec86c394364f0301471e1c1ac9784086f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324834"
---
# <a name="configure-operator-connect"></a>Konfigurieren von Operator Connect

>[!NOTE]
>Operator Connect ist derzeit nur in der **öffentlichen Vorschau** verfügbar. Die öffentliche Vorschau bietet Ihnen die Möglichkeit, kommende Funktionen zu testen und Feedback zu geben. Die in der öffentlichen Vorschau enthaltenen Features sind u. U. nicht vollständig, könnten geändert werden und werden in Office 365 Government Clouds nicht unterstützt.

In diesem Artikel wird beschrieben, wie diese Einstellungen konfiguriert werden. Lesen Sie vor dem Konfigurieren von Operator Connect [Planen für Operator Connect](operator-connect-plan.md), um sich über Voraussetzungen und Lizenzierung zu informieren.

## <a name="enable-an-operator"></a>Einen Anbieter aktivieren

Sie können Anbieter im Microsoft Teams Admin Center aktivieren, bearbeiten und entfernen. Navigieren Sie im linken Navigationsbereich zu **Voice > Anbieter**.

So aktivieren Sie einen Anbieter:

1. **Wählen Sie einen Anbieter aus.** Filtern Sie auf der Registerkarte **Alle Anbieter** verfügbare Anbieter nach Region oder Dienst, um den geeigneten Anbieter für Ihre Anrufanforderungen zu finden. Wählen Sie dann den Anbieter aus, den Sie aktivieren möchten.  

2. **Wählen Sie Länder aus.** Wählen Sie unter **Anbietereinstellungen** die Länder aus, die Sie mit dem ausgewählten Anbieter aktivieren möchten.

3. **Geben Sie Kontaktinformationen an (optional).** Wenn Sie möchten, dass Anbieter Ihnen zusätzliche Informationen zu Operator Connect bereitstellen, aktivieren Sie das Kontrollkästchen und geben Sie Ihre Kontaktinformationen an.  

4. **Stimmen Sie dem Hinweis zur Datenübertragung zu.**

5. **Fügen Sie Ihren Anbieter hinzu.** Klicken Sie zum Speichern auf **Als meinen Anbieter hinzufügen**.

## <a name="set-up-phone-numbers"></a>Telefonnummern einrichten

Wie Telefonnummern eingerichtet werden, hängt davon ab, ob Sie Nummern für neue Benutzer einrichten oder vorhandene Nummern aus Microsoft-Anrufplänen oder Direct Routing verschieben möchten.

- Wenn Sie Telefonnummern für neue Benutzer beziehen müssen, lesen Sie [Beziehen von Nummern für neue Microsoft Teams-Benutzer](#acquire-numbers-for-new-teams-users).

- Wenn Sie vorhandene Nummern aus Anrufplänen zu Operator Connect verschieben möchten, lesen Sie [Verschieben von Nummern aus Anrufplänen zu Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).

- Wenn Sie vorhandene Nummern von Direct Routing zu Operator Connect verschieben möchten, lesen Sie [Verschieben von Nummern von Direct Routing zu Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).

>[!IMPORTANT]
>**Notfalladressen:** Telefonnummern, die Notfalladressen zugeordnet sind, werden von Ihrem Anbieter verwaltet. Nachdem Sie Notfalladressen im Microsoft Teams Admin Center erstellt haben, weist Ihr Anbieter diesen Notfalladressen Telefonnummern zu. Wenn Sie Änderungen an Notfalladressen und den ihnen zugewiesenen Telefonnummern vornehmen möchten, wenden Sie sich an Ihren Anbieter.

### <a name="acquire-numbers-for-new-teams-users"></a>Telefonnummern für neue Microsoft Teams-Benutzer beziehen

Führen Sie die folgenden Schritte aus, um Nummern für neue Microsoft Teams-Benutzer zu erhalten:

1. **Weisen Sie eine Telefonsystem-Lizenz zu.** Sie können Ihren Benutzern über das Microsoft 365 Admin Center oder mithilfe von PowerShell eine Telefonsystemlizenz zuweisen. Weitere Informationen finden Sie unter [Benutzern Microsoft Teams-Add-On-Lizenzen zuweisen](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **Stellen Sie sicher, dass Sie sich im TeamsOnly-Modus befinden.** Um zu überprüfen, ob sich Ihre Organisation im TeamsOnly-Modus befindet, wechseln Sie im Microsoft Teams Admin Center zu **Organisationsweite Einstellungen > Microsoft Teams-Upgrade**. Um zu überprüfen, ob sich ein Benutzer im TeamsOnly-Modus befindet, wechseln Sie zu **Benutzer**, und wählen Sie das entsprechende Benutzerkonto aus. Überprüfen Sie auf der Registerkarte **Konto** unter **Microsoft Teams-Upgrade**, ob Ihr Koexistenzmodus auf "Nur Microsoft Teams" festgelegt ist.

3. **Erstellen und überprüfen Sie Notfalladressen.** Wechseln Sie zum Einrichten von Notfalladressen im Microsoft Teams Admin Center zu **Standorte > Notfalladressen**. Weitere Informationen finden Sie unter [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md).

4. **Beziehen Sie Telefonnummern.** Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Eine Liste von Anbieterwebsites finden Sie unter [Anbieter](#operators). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

5. **Weisen Sie Nummern zu.** Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Telefonnummern aus Anrufplänen zu Operator Connect verschieben

1. Wenden Sie sich an Ihren Anbieter, um Ihre Nummern zu Operator Connect zu portieren. Unter [Anbieter](#operators) finden Sie die Website Ihres Anbieters.

2. Nachdem Ihr Anbieter den Portierungsauftrag abgeschlossen hat, können Sie die Zuweisung von Anrufplan-Telefonnummern Ihrer Benutzer aufheben und die Anrufplanlizenz entfernen. Anschließend kann Ihr Anbieter die Nummern in Ihren Mandanten hochladen.

3. Weisen Sie Benutzern Operator Connect-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Telefonnummern von Direct Routing zu Operator Connect verschieben

1. Entfernen Sie die vorhandene Telefonnummer von einem Benutzer wie folgt:  

   Rufen Sie den bestehenden lokalen Anschluss-URI ab, indem Sie den folgenden PowerShell-Befehl ausführen:

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   Entfernen Sie den bestehenden lokalen Anschluss-URI, indem Sie den folgenden PowerShell-Befehl ausführen:  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. Entfernen Sie alle PSTNUsage-Elemente, die Ihren Benutzern zugeordnet sind. Andernfalls werden Anrufe an das Gateway weitergeleitet, das in PSTNUsage angegeben ist. Informationen zum Entfernen von PSTNUsage finden Sie unter [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).

3. Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Eine Liste von Anbieterwebsites finden Sie unter [Anbieter](#operators). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

4. Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Operator Connect-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

   

### <a name="assign-numbers"></a>Telefonnummern zuweisen

Unabhängig davon, ob Sie neue Microsoft Teams-Benutzer hinzufügen oder vorhandene Benutzer auf Operator Connect umstellen, gehen Sie wie folgt vor, um Telefonnummern zuzuweisen:

Um Nummern mithilfe des Microsoft Teams Admin Centers zuzuweisen, wechseln Sie zu **Telefonnummern**. Die Schritte sind dieselben wie beim Zuweisen von Nummern für Anrufpläne. Weitere Informationen finden Sie unter [Einem Benutzer eine Telefonnummer zuweisen](assign-change-or-remove-a-phone-number-for-a-user.md).

Um Telefonnummern mithilfe von PowerShell zuzuweisen, verwenden Sie das Cmdlet "Set-CsOnlineVoiceUser" wie folgt:

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

Zum Beispiel: 

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

Weitere Informationen zum Zuweisen von Telefonnummern finden Sie unter [Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](assign-change-or-remove-a-phone-number-for-a-user.md).



## <a name="manage-your-operators"></a>Anbieter verwalten

Auf der Registerkarte "Meine Anbieter" können Sie Ihre Anbieter und deren Status einsehen und die folgenden Änderungen an Ihrer Auswahl vornehmen:  

- Anbieterdienste nach Land verwalten
- Einen Anbieter anhalten
- Einen Anbieter entfernen

> [!NOTE]
> Bevor Sie einen Anbieter aus Ihrer Organisation oder aus einem Land entfernen, müssen Sie alle Telefonnummern entfernen, die Benutzern in der Organisation oder dem Land zugewiesen sind, und den Anbieter kontaktieren, um die Nummern freizugeben.

## <a name="operators"></a>Anbieter

Sie können Telefonnummern von den folgenden Anbietern beziehen, indem Sie zu den hier verlinkten Websites wechseln:


|Anbieter  |Website des Anbieters  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
