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
description: Hier finden Sie weitere Informationen zum Konfigurieren von Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947577"
---
# <a name="configure-operator-connect"></a>Konfigurieren von Operator Connect

>[!NOTE]
>Operator Connect ist derzeit nur in Public **Preview verfügbar.** In der öffentlichen Vorschau können Sie anstehende Features testen und Feedback geben. Features, die in Public Preview enthalten sind, sind möglicherweise nicht vollständig, werden möglicherweise geändert und werden in Office 365 Government Clouds nicht unterstützt.

In diesem Artikel wird beschrieben, wie Sie Operator Connect konfigurieren. Lesen Sie vor dem Konfigurieren von Operator Connect planen für [Operator Connect,](operator-connect-plan.md) um Informationen zu Voraussetzungen und Lizenzierung zu erhalten.

## <a name="enable-an-operator"></a>Aktivieren eines Operators

Sie können Operatoren im Teams Admin Center aktivieren, bearbeiten und entfernen. Wechseln Sie im linken Navigationsbereich zu Sprach **> Operatoren**.

So aktivieren Sie einen Operator:

1. **Wählen Sie einen Operator aus.** Filtern Sie **auf der Registerkarte Alle** Operatoren die verfügbaren Operatoren nach Region oder Dienst, um die richtige Operator für Ihre Sprachanforderungen zu finden. Wählen Sie dann den Operator aus, den Sie aktivieren möchten.  

2. **Wählen Sie Länder aus.** Wählen **Sie unter Operatoreinstellungen** die Länder aus, die Sie mit dem ausgewählten Operator aktivieren möchten.

3. **Geben Sie Kontaktinformationen an (optional).** Wenn Sie möchten, dass die Operatoren weitere Informationen zu Operator Connect erhalten, aktivieren Sie das Kontrollkästchen, und geben Sie Ihre Kontaktinformationen an.  

4. **Akzeptieren Sie die Benachrichtigung über die Datenübertragung.**

5. **Fügen Sie Ihren Operator hinzu.** Wählen **Sie zum Speichern Als Operator hinzufügen** aus.

## <a name="set-up-phone-numbers"></a>Einrichten von Telefonnummern

Wie Sie Telefonnummern einrichten, hängt davon ab, ob Sie Nummern für neue Benutzer einrichten oder vorhandene Nummern aus Microsoft-Anrufplänen oder Direct Routing verschieben.

- Wenn Sie Telefonnummern für neue Benutzer erwerben müssen, lesen Sie Erwerben [von Nummern für neue Teams-Benutzer.](#acquire-numbers-for-new-teams-users)

- Wenn Sie vorhandene Nummern von Anrufplänen in Operator Connect verschieben möchten, lesen Sie Verschieben von Nummern von Anrufplänen [in Operator Connect.](#move-numbers-from-calling-plans-to-operator-connect)

- Informationen zum Verschieben vorhandener Nummern von Direct Routing zu Operator Connect finden Sie unter Verschieben von Nummern [von Direct Routing zu Operator Connect.](#move-numbers-from-direct-routing-to-operator-connect)

>[!IMPORTANT]
>**Notfalladressen:** Telefonnummern, die Notfalladressen zugeordnet sind, werden von Ihrem Netzbetreiber verwaltet. Nachdem Sie im Teams Admin Center Notfalladressen erstellt haben, weist Ihr Netzbetreiber diesen Notfalladressen Telefonnummern zu. Wenn Sie Änderungen an Notfalladressen und den ihnen zugewiesenen Telefonnummern vornehmen müssen, wenden Sie sich an Ihren Netzbetreiber.

### <a name="acquire-numbers-for-new-teams-users"></a>Erwerben von Nummern für neue Teams-Benutzer

Führen Sie die folgenden Schritte aus, um Nummern für neue Teams-Benutzer zu erhalten:

1. **Weisen Sie eine Telefonsystemlizenz zu.** Sie können Ihren Benutzern über das Microsoft 365 Admin Center oder mithilfe von PowerShell eine Telefonsystemlizenz zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Teams-Add-On-Lizenzen zu Benutzern.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. **Vergewissern Sie sich, dass Sie sich nur im Teams-Modus befinden.** Um zu überprüfen, ob Sich Ihre Organisation nur im **Teams-Modus** befindet, wechseln Sie im Teams Admin Center zu Organisationsweite Einstellungen > Teams-Upgrade . Um zu überprüfen, ob sich ein Benutzer nur im Teams-Modus befindet, wechseln Sie **zu Benutzer,** und wählen Sie ein Benutzerkonto aus. Überprüfen Sie **auf der** Registerkarte Konto unter **Teams-Upgrade,** ob der Koexistenzmodus auf "Nur Teams" festgelegt ist.

3. **Erstellen und überprüfen Sie Notfalladressen.** Wechseln Sie im Teams Admin Center zu Standorte **> Notfalladressen,** um Notfalladressen zu einrichten. Weitere Informationen finden Sie unter Hinzufügen, Ändern oder Entfernen eines [Notfallstandorts für Ihre Organisation.](add-change-remove-emergency-location-organization.md)

4. **Erwerben von Nummern** Wechseln Sie zur Website Ihrer Netzbetreiber, um Telefonnummern zu bestellen und zu erwerben. Eine Liste der Operatorwebsites finden Sie unter [Operatoren.](#operators) Sie müssen Ihre Mandanten-ID bereitstellen. Wenn Sie Ihre Mandanten-ID nicht kennen, finden Sie weitere Informationen unter Suchen [Ihrer Microsoft 365-Mandanten-ID.](/onedrive/find-your-office-365-tenant-id)

5. **Weisen Sie Nummern zu.** Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, werden Nummern in Ihren Mandanten hochgeladen. Sie können die Nummern und den Anbieter im Teams Admin Center anzeigen, indem Sie zu **Voicemail- > Telefonnummern wechseln.** Weisen Sie Benutzern Nummern über das Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Nummern.](#assign-numbers)
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Verschieben von Nummern aus Anrufplänen in "Operator Connect"

1. Wenden Sie sich an Ihren Netzbetreiber, um Ihre Nummern zu Operator Connect zu portieren. Informationen [zur Website](#operators) ihres Anbieters finden Sie unter Operatoren.

2. Nachdem Ihr Netzbetreiber den Portierungsauftrag abgeschlossen hat, können Sie die Anrufplan-Telefonnummern Ihrer Benutzer entfernen und die Anrufplanlizenz entfernen. Anschließend kann Ihr Netzbetreiber die Nummern in Ihren Mandanten hochladen.

3. Zuweisen von Operator Connect-Nummern zu Benutzern über das Teams Admin Center oder mithilfe von PowerShell. Weitere Informationen finden Sie unter [Zuweisen von Nummern.](#assign-numbers)

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Verschieben von Nummern von Direct Routing zu Operator Connect

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

3. Wechseln Sie zur Website Ihrer Netzbetreiber, um Telefonnummern zu bestellen und zu erwerben. Eine Liste der Operatorwebsites finden Sie unter [Operatoren.](#operators) Sie müssen Ihre Mandanten-ID bereitstellen. Wenn Sie Ihre Mandanten-ID nicht kennen, finden Sie weitere Informationen unter Suchen [Ihrer Microsoft 365-Mandanten-ID.](/onedrive/find-your-office-365-tenant-id)

4. Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, werden Nummern in Ihren Mandanten hochgeladen. Sie können die Nummern und den Anbieter im Teams Admin Center anzeigen, indem Sie zu **Voicemail- > Telefonnummern wechseln.** Zuweisen von Operator Connect-Nummern zu Benutzern über das Teams Admin Center oder mithilfe von PowerShell. Weitere Informationen finden Sie unter [Zuweisen von Nummern.](#assign-numbers)

   

### <a name="assign-numbers"></a>Zuweisen von Nummern

Ganz gleich, ob Sie neue Teams-Benutzer hinzufügen oder vorhandene Benutzer in Operator Connect verschieben, die Schritte zum Zuweisen von Nummern sind wie folgt:

Zum Zuweisen von Nummern über das Teams Admin Center wechseln Sie **zu Telefonnummern.** Die Schritte sind mit dem Zuweisen von Nummern für Anrufpläne identisch. Weitere Informationen finden Sie unter [Zuweisen einer Telefonnummer zu einem Benutzer.](assign-change-or-remove-a-phone-number-for-a-user.md)

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
