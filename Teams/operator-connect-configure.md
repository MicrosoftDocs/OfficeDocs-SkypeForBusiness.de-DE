---
title: Konfigurieren der Verbinden
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
description: Hier finden Sie weitere Informationen zum Konfigurieren von Operatoren Verbinden.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689902"
---
# <a name="configure-operator-connect"></a>Konfigurieren der Verbinden

>[!NOTE]
>Operatoren Verbinden derzeit nur in der **öffentlichen Vorschau verfügbar.** In der öffentlichen Vorschau können Sie anstehende Features testen und Feedback geben. Features, die in public preview enthalten sind, sind möglicherweise nicht vollständig, werden möglicherweise geändert und werden in Office 365 Government unterstützt.

In diesem Artikel wird beschrieben, wie Sie Operatoren Verbinden. Lesen Sie vor Verbinden der Konfiguration [](operator-connect-plan.md) von Operatoren die Informationen zu Verbinden und Lizenzierung planen für Operatoren.

## <a name="enable-an-operator"></a>Aktivieren eines Operators

Sie können Operatoren im Admin Center aktivieren, Teams und entfernen. Wechseln Sie im linken Navigationsbereich zu Sprach **> Operatoren**.

So aktivieren Sie einen Operator:

1. **Wählen Sie einen Operator aus.** Filtern Sie **auf der Registerkarte Alle** Operatoren die verfügbaren Operatoren nach Region oder Dienst, um die richtige Operator für Ihre Sprachanforderungen zu finden. Wählen Sie dann den Operator aus, den Sie aktivieren möchten.  

2. **Wählen Sie Länder aus.** Wählen **Sie unter Operatoreinstellungen** die Länder aus, die Sie mit dem ausgewählten Operator aktivieren möchten.

3. **Geben Sie Kontaktinformationen an (optional).** Wenn Sie möchten, dass operatoren Sie mit zusätzlichen Informationen zu den Operatoren Verbinden, aktivieren Sie das Kontrollkästchen, und geben Sie Ihre Kontaktinformationen ein.  

4. **Akzeptieren Sie die Benachrichtigung über die Datenübertragung.**

5. **Fügen Sie Ihren Operator hinzu.** Wählen **Sie zum Speichern Als Operator hinzufügen** aus.

## <a name="set-up-phone-numbers"></a>Einrichten von Telefonnummern

Wie Sie Telefonnummern einrichten, hängt davon ab, ob Sie Nummern für neue Benutzer einrichten oder vorhandene Nummern aus Microsoft-Anrufplänen oder Direct Routing verschieben.

- Wenn Sie Telefonnummern für neue Benutzer erwerben müssen, lesen Sie Erwerben von Telefonnummern [für neue Teams Benutzer.](#acquire-numbers-for-new-teams-users)

- Wenn Sie vorhandene Nummern von Anrufplänen in die Anbieter Verbinden, lesen Sie Verschieben von Nummern von Anrufplänen zu [Netzbetreibern Verbinden.](#move-numbers-from-calling-plans-to-operator-connect)

- Wenn Sie vorhandene Nummern aus dem Direktrouting in das Operator-Routing verschieben Verbinden, lesen Sie Verschieben von Nummern von Direct [Routing zu Operator Verbinden.](#move-numbers-from-direct-routing-to-operator-connect)

>[!IMPORTANT]
>**Notfalladressen:** Notfalladressen, die mit einer Nummer verknüpft sind, die vom Netzbetreiber erworben wurde, werden direkt mit dem Anbieter verwaltet. Wenden Sie sich an den Netzbetreiber, um Änderungen vorzunehmen.

### <a name="acquire-numbers-for-new-teams-users"></a>Erwerben von Nummern für neue Teams Benutzer

Führen Sie die folgenden Schritte aus, um Teams neuen Benutzern zu erwerben:

1. **Weisen Sie eine Telefonsystem zu.** Sie können Ihren Telefonsystem über das Admin Center Microsoft 365 oder Mithilfe von PowerShell eine Lizenz zuweisen. Weitere Informationen finden Sie unter [Zuweisen Teams Add-On-Lizenzen zu Benutzern.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. **Vergewissern Sie sich, dass Sie sich im TeamsOnly-Modus befinden.** Um dies zu überprüfen, wechseln Teams Admin Center zu **Organisationsweite Einstellungen**> Teams Upgrade. Der Koexistenzmodus sollte nur auf "Teams festgelegt werden.

3. **Erstellen und überprüfen Sie Notfalladressen.** Wechseln Sie Teams Admin Center zu Standorte **> Notfalladressen,** um Notfalladressen zu richten. Weitere Informationen finden Sie unter Hinzufügen, Ändern oder Entfernen eines [Notfallstandorts für Ihre Organisation.](add-change-remove-emergency-location-organization.md)

4. **Erwerben von Nummern** Wechseln Sie zur Website Ihrer Netzbetreiber, um Telefonnummern zu bestellen und zu erwerben. Eine Liste der Operatorwebsites finden Sie unter [Operatoren.](#operators) Sie müssen Ihre Mandanten-ID bereitstellen. Wenn Sie Ihre Mandanten-ID nicht kennen, finden Sie weitere Informationen unter Microsoft 365 [Mandanten-ID.](/onedrive/find-your-office-365-tenant-id)

5. **Weisen Sie Nummern zu.** Nachdem Ihr Operator die Bestellung abgeschlossen hat, werden Testnummern in Ihren Mandanten hochgeladen. Sie können die Nummern und den Anbieter im Teams Admin Center anzeigen, indem Sie zu **Voice-> Telefon wechseln.** Weisen Sie Benutzern Nummern mithilfe des Teams Admin Centers oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Nummern.](#assign-numbers)
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Verschieben von Nummern aus Anrufplänen zu Verbinden

1. Wenden Sie sich an Ihren Netzbetreiber, um Ihre Nummern zu operator Verbinden. Informationen [zur Website](#operators) ihres Anbieters finden Sie unter Operatoren.

2. Nachdem Ihr Netzbetreiber den Portierungsauftrag abgeschlossen hat, können Sie die Anrufplan-Telefonnummern Ihrer Benutzer entfernen und die Anrufplanlizenz entfernen. Anschließend kann Ihr Netzbetreiber die Nummern in Ihren Mandanten hochladen.

3. Weisen Sie Verbinden mithilfe des Teams Admin Centers oder mithilfe von PowerShell Operator-Nummern zu. Weitere Informationen finden Sie unter [Zuweisen von Nummern.](#assign-numbers)

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Verschieben von Nummern aus dem direkten Routing in die Verbinden

1. Entfernen Sie die vorhandene Telefonnummer wie folgt aus dem Benutzer:  

   Den vorhandenen "On-prem Line"-URI erhalten Sie, indem Sie den folgenden PowerShell-Befehl ausführen:

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   Entfernen Sie den "On-prem Line"-URI, indem Sie den folgenden PowerShell-Befehl ausführen:  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. Entfernen Sie alle PSTNUsage, die Ihren Benutzern zugeordnet sind, andernfalls werden Anrufe an das Gateway geroutet, das in der PSTN-Nutzung angegeben ist. Informationen zum Entfernen der PSTN-Verwendung finden Sie unter [Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)

3. Wechseln Sie zur Website Ihrer Netzbetreiber, um Telefonnummern zu bestellen und zu erwerben. Eine Liste der Operatorwebsites finden Sie unter [Operatoren.](#operators) Sie müssen Ihre Mandanten-ID bereitstellen. Wenn Sie Ihre Mandanten-ID nicht kennen, finden Sie weitere Informationen unter Microsoft 365 [Mandanten-ID.](/onedrive/find-your-office-365-tenant-id)

4. Nachdem Ihr Operator die Bestellung abgeschlossen hat, werden Testnummern in Ihren Mandanten hochgeladen. Sie können die Nummern und den Anbieter im Teams Admin Center anzeigen, indem Sie zu **Voice-> Telefon wechseln.** Weisen Sie Verbinden mithilfe des Teams Admin Centers oder mithilfe von PowerShell Operator-Nummern zu. Weitere Informationen finden Sie unter [Zuweisen von Nummern.](#assign-numbers)

   

### <a name="assign-numbers"></a>Zuweisen von Nummern

Ganz gleich, ob Sie Teams Benutzer hinzufügen oder vorhandene Benutzer in die Operator-Verbinden verschieben, die Schritte zum Zuweisen von Nummern sind wie folgt:

Um Nummern über das Teams Admin Center zuzuordnen, wechseln Sie **zu Telefon Nummern**. Die Schritte sind mit dem Zuweisen von Nummern für Anrufpläne identisch. Weitere Informationen finden Sie unter [Zuweisen einer Telefonnummer zu einem Benutzer.](assign-change-or-remove-a-phone-number-for-a-user.md)

Zum Zuweisen von Nummern mithilfe von PowerShell verwenden Sie das cmdlet Set-CsOnlineVoiceUser Wie folgt:

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

Beispiel:

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

Weitere Informationen zum Zuweisen von Telefonnummern zu Ihren Benutzern finden Sie unter Zuweisen, Ändern oder Entfernen einer [Telefonnummer für einen Benutzer.](assign-change-or-remove-a-phone-number-for-a-user.md)



## <a name="manage-your-operators"></a>Verwalten der Operatoren

Auf der Registerkarte Meine Operatoren können Sie die Operatoren und deren Status anzeigen und die folgenden Änderungen an Ihrer Auswahl vornehmen:  

- Verwalten von Operatordiensten nach Land
- Anhalten eines Operators
- Entfernen eines Operators

> [!NOTE]
> Bevor Sie einen Netzbetreiber aus Ihrer Organisation oder einem Land entfernen, müssen Sie alle Telefonnummern entfernen, die Benutzern in der Organisation oder im Land zugewiesen sind, und sich an den Netzbetreiber wenden, um die Nummern frei zu geben.

## <a name="operators"></a>Operatoren

Sie können Telefonnummern der folgenden Operatoren erwerben, indem Sie zu den hier verknüpften Websites gehen:


|Vermittlung  |Website der Operatoren  |
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
