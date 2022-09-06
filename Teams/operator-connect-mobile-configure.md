---
title: Konfigurieren von Telefonieanbieter mit Mobil
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
description: Mer informasjon zum Konfigurieren Telefonieanbieter mit Mobil.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca49ac8cb74bcb61cd8c1d8fc2056c69a89d715
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606880"
---
# <a name="configure-operator-connect-mobile"></a>Konfigurieren von Telefonieanbieter mit Mobil

**Telefonieanbieter mit Mobil ist eine öffentliche Vorschauversion.** Eine Liste der Betreiber, die am Microsoft Telefonieanbieter mit Mobil-Programm teilnehmen, sowie die Länder oder Regionen, in denen ihr Dienst verfügbar ist, finden Sie unter [Microsoft 365 Telefonieanbieter mit Mobil](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/connect-mobile).

In diesem Artikel wird beschrieben, wie Sie Telefonieanbieter mit Mobil konfigurieren. Lesen Sie vor dem Konfigurieren von Telefonieanbieter mit Mobil "[Plan for Telefonieanbieter mit Mobil](operator-connect-mobile-plan.md)" nach, um Informationen zu Vorteilen, Voraussetzungen und Lizenzierung zu erhalten.

## <a name="enable-an-operator"></a>Einen Anbieter aktivieren

Sie können Operatoren im Teams Admin Center aktivieren, bearbeiten und entfernen. Navigieren Sie im linken Navigationsbereich zu **Voice > Anbieter**.

So aktivieren Sie einen Anbieter:

1. Wählen Sie einen Operator aus, der Telefonieanbieter mit Mobil unterstützt. Filtern Sie auf der Registerkarte **"Alle Operatoren**" die verfügbaren Operatoren nach Region oder Dienst, um den richtigen Operator zu finden, der Telefonieanbieter mit Mobil unterstützt. Wählen Sie dann den Anbieter aus, den Sie aktivieren möchten.

2. Wählen Sie unter **Anbietereinstellungen** die Länder aus, die Sie mit dem ausgewählten Anbieter aktivieren möchten.

3. **Geben Sie Kontaktinformationen an.** Ihre Kontaktinformationen, einschließlich Ihres vollständigen Namens und Ihrer E-Mail-Adresse, werden automatisch an Ihren Betreiber weitergegeben. Sie können diese Informationen später ändern. Darüber hinaus müssen Sie die Unternehmensgröße angeben, und Sie haben die Möglichkeit, Ihre Telefonnummer anzugeben. Operatoren verwenden diese Informationen, um Sie mit weiteren Details zu Telefonieanbieter mit Mobil zu kontaktieren.

4. Stimmen Sie dem Hinweis zur Datenübertragung zu.

5. Klicken Sie zum Speichern auf **Als meinen Anbieter hinzufügen**.

## <a name="set-up-phone-numbers"></a>Telefonnummern einrichten

Wenn Sie Ihre bestehenden kostenpflichtigen SIM-fähigen Telefonnummern zu Teams hinzufügen möchten, wenden Sie sich an Ihren Betreiber, um sicherzustellen, dass Sie über das berechtigte Telefonieanbieter mit Mobil-Abonnement verfügen, und diese können Ihre Nummern in Teams hochladen. Nachdem Ihr Operator die Bestellung abgeschlossen hat, können Sie diese Nummern Benutzern zuweisen. 

Die Website Ihres Betreibers finden Sie im [Microsoft 365 Operator Connect-Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen [Sie "Suchen Ihrer Microsoft 365-Mandanten-ID"](/onedrive/find-your-office-365-tenant-id.md). Möglicherweise portieren Sie eine vorhandene Festnetztelefonnummer oder Festnetznummer zu einem Wireless Voice-Abonnement, wenn es in Ihrer Region und von Ihrem Betreiber unterstützt wird. 

Wie Sie Telefonnummern einrichten, hängt davon ab, ob Sie Nummern für neue Benutzer einrichten oder vorhandene Nummern aus Microsoft-Anrufplänen, Telefonieanbieter oder Direct Routing verschieben.

- [Erwerben Sie Nummern für neue Teams-Benutzer](#acquire-numbers-for-new-teams-users).  

- [Verschieben von Nummern aus Anrufplänen in Telefonieanbieter mit Mobil](#move-numbers-from-calling-plans-to-operator-connect-mobile).  

- [Verschieben von Zahlen von Operator Connect zu Telefonieanbieter mit Mobil](#move-numbers-from-operator-connect-to-operator-connect-mobile).  

- [Verschieben von Nummern von Direct Routing zu Telefonieanbieter mit Mobil](#move-numbers-from-direct-routing-to-operator-connect-mobile).  


### <a name="assign-numbers-to-emergency-addresses"></a>Zuweisen von Nummern zu Notfalladressen

Die Notfalladresse ist ein statischer Ort, der einer Nummer zugeordnet ist, wenn über Microsoft Teams-Endpunkte/-Clients zugegriffen werden kann. Nachdem Sie Notfalladressen im Teams Admin Center erstellt haben, hängt es von Ihrem Operator ab, wie Sie die Adressen zuweisen oder später ändern.

Um Notrufadressen, die von Microsoft Teams-Endpunkten verwendet werden, Nummern zuzuweisen, implementiert Ihr Operator eines von drei Szenarien:

- Der Operator weist den Telefonnummern Notfalladressen zu und ermöglicht Es Ihnen, diese später im Teams Admin Center zu ändern.

- Der Operator weist keine Adressen zu und ermöglicht Es Ihnen, den Telefonnummern im Teams Admin Center Notfalladressen zuzuweisen.

- Der Operator weist den Telefonnummern Notfalladressen zu und lässt keine Änderung zu. In diesem Szenario müssen Sie sich an Ihren Betreiber wenden, um Änderungen an Telefonnummern und deren zugewiesener Notfalladresse vorzunehmen.

Wenn Anrufe über die systemeigene Wählhilfe des SIM-fähigen Smartphones getätigt werden, kann Ihr Betreiber die geografischen Koordinaten oder den Zellturm für die Behandlung des Anrufs verwenden, um den Notfallstandort näherungsweise zu unterstützen.

Weitere Informationen zu Notrufen finden [Sie unter Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md) und [Planen und Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md).

### <a name="acquire-numbers-for-new-teams-users"></a>Telefonnummern für neue Microsoft Teams-Benutzer beziehen

Führen Sie die folgenden Schritte aus, um Nummern für neue Microsoft Teams-Benutzer zu erhalten:

1. **Weisen Sie eine Telefonsystemlizenz und eine Telefonieanbieter mit Mobil Add-On-Lizenz zu.** Sie können Ihren Benutzern über die Microsoft 365 Admin Center oder mithilfe von PowerShell eine Telefonsystemlizenz und eine Telefonieanbieter mit Mobil-Add-On-Lizenz zuweisen. Weitere Informationen finden Sie unter [Benutzern Microsoft Teams-Add-On-Lizenzen zuweisen](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **Benutzer, denen Telefonnummern zugewiesen werden, die mit Telefonieanbieter mit Mobil erworben werden, müssen sich im TeamsOnly-Modus befinden.** Wenn sich Ihre Organisation im TeamsOnly-Modus befindet, befinden sich alle Ihre Benutzer im TeamsOnly-Modus. 

   Um dies zu überprüfen, wechseln Sie im Teams Admin Center zu **Teams > Teams-Upgradeeinstellungen**. Wenn sich Ihre Organisation im Inselmodus befindet, überprüfen Sie, ob sich bestimmte Benutzer im TeamsOnly-Modus befinden. Wechseln **Sie zu "Benutzer"** , und wählen Sie ein Benutzerkonto aus. Auf der Registerkarte **"Konto"** unter " **Teams-Upgrade** " sollte der Koexistenzmodus auf "TeamsOnly" festgelegt sein.

3. **Beziehen Sie Telefonnummern.** Wechseln Sie zur Website Ihres Betreibers, oder kontaktieren Sie sie, um mobiltelefonfähige SIM-fähige Telefonnummern mit aktiviertem Telefonieanbieter mit Mobil-Dienst zu bestellen und zu erwerben. 

   Nachdem Ihr Betreiber die Bestellung abgeschlossen hat, lädt er SIM-fähige Mobiltelefonnummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. 

4. **Weisen Sie Nummern zu.** Sie können Benutzern Nummern über das Teams Admin Center oder mithilfe von PowerShell zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect-mobile"></a>Verschieben von Nummern aus Anrufplänen in Telefonieanbieter mit Mobil

1. Stellen Sie sicher, dass Sie über berechtigte Microsoft 365-Abonnements für Telefonieanbieter mit Mobil und die Telefonieanbieter mit Mobil-Add-On-Lizenz verfügen. Sie müssen [die Telefonnummer entfernen, die für die jeweiligen Benutzer verschoben werden soll](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). 

2. Wenden Sie sich an Ihren Betreiber, um Ihre Telefonnummern zu Telefonieanbieter mit Mobil in einem berechtigten, simfähigen Wlan-VoIP-Plan zu portieren. 

3. Nachdem Der Betreiber den Portierungsauftrag abgeschlossen hat, lädt der Betreiber die Nummern in Ihren Mandanten hoch.  Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. 

4. Sie können Benutzern Nummern mithilfe des Teams Admin Centers oder mithilfe von PowerShell zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-operator-connect-to-operator-connect-mobile"></a>Verschieben von Nummern von Operator Connect zu Telefonieanbieter mit Mobil

1. Stellen Sie sicher, dass Sie über berechtigte Microsoft 365-Abonnements für Telefonieanbieter mit Mobil und die Add-On-Lizenz "Operator Connect" verfügen. Sie müssen [die Telefonnummer entfernen, die für die jeweiligen Benutzer verschoben werden soll](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). Wenden Sie sich an Ihren vorhandenen Anbieter von Telefonieanbietern, um die Telefonnummern aus Ihrem Mandanten zu entfernen.

2. Wenden Sie sich an Ihren Betreiber, um Ihre Telefonnummern zu Telefonieanbieter mit Mobil in einem berechtigten, simfähigen Wlan-VoIP-Plan zu portieren. 

3. Nachdem Der Betreiber den Portierungsauftrag abgeschlossen hat, lädt der Betreiber die Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. 

4. Sie können Benutzern Nummern mithilfe des Teams Admin Centers oder mithilfe von PowerShell zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-direct-routing-to-operator-connect-mobile"></a>Verschieben von Nummern von Direct Routing zu Telefonieanbieter mit Mobil   

Um Nummern von Direct Routing zu Telefonieanbieter mit Mobil zu verschieben, müssen Sie die folgenden Schritte ausführen:

1. [Ermitteln Sie, ob die vorhandenen Direct Routing-Nummern online oder lokal zugewiesen werden](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises).

2. [Migrieren Sie die Nummern von Direct Routing zu Telefonieanbieter mit Mobil](#migrate-the-numbers-from-direct-routing-to-operator-connect-mobile).

2. [Entfernen Sie die Online-VoIP-Routingrichtlinie, die Ihrem Benutzer zugeordnet ist](#remove-the-online-voice-routing-policy-associated-with-your-user).

3. [Erwerben Sie Telefonnummern](#acquire-phone-numbers).

4. [Weisen Sie Telefonnummern zu](#assign-phone-numbers).

Diese Schritte werden in den folgenden Abschnitten ausführlicher beschrieben.

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Ermitteln Sie, ob die vorhandenen Direct Routing-Nummern online oder lokal zugewiesen werden.

Wie Sie Ihre vorhandenen Direct Routing-Nummern entfernen, hängt davon ab, ob die Nummer lokal oder online zugewiesen ist.

1. Überprüfen Sie zunächst, ob dem Benutzer eine Direct Routing-Nummer zugewiesen ist, indem Sie den folgenden Teams PowerShell-Befehl ausführen. NumberType sollte DirectRouting sein:

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. Ermitteln Sie, ob die Nummer online oder lokal zugewiesen ist, indem Sie den folgenden Teams PowerShell-Befehl ausführen:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   Wenn OnPremLineUri mit einer E.164-Telefonnummer aufgefüllt wird, wurde die Telefonnummer lokal zugewiesen und mit Microsoft 365 synchronisiert.

#### <a name="migrate-the-numbers-from-direct-routing-to-operator-connect-mobile"></a>Migrieren der Nummern von Direct Routing zu Telefonieanbieter mit Mobil

Führen Sie die folgenden Schritte aus, um Nummern zu migrieren.  

> [!Important]
> Während der Migration ist die Telefonnummer nicht mehr verfügbar. Koordinieren Sie dies mit Dem Operator Connect-Operator, bevor Sie mit der Migration beginnen.

- **Wenn Sie vorhandene Direct Routing-Nummern, die online zugewiesen sind, zu Telefonieanbieter mit Mobil migrieren** möchten, wenden Sie sich an Ihren Betreiber. Informationen zur Website Ihres Betreibers finden Sie im [Microsoft 365 Operator Connect-Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Am vereinbarten Datum und der vereinbarten Uhrzeit migriert Ihr Betreiber Ihre Nummern von Direct Routing zu Telefonieanbieter mit Mobil. Dies kann dazu führen, dass Die Telefonnummer, die von Ihrem Mandanten migriert wird, entfernt und erneut als neue Telefonnummer hinzugefügt wird, die Telefonieanbieter mit Mobil zugeordnet ist.

- **Um lokale Direct Routing-Nummern zu Telefonieanbieter mit Mobil zu migrieren**, führen Sie den folgenden Skype for Business Server PowerShell-Befehl aus:

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  Führen Sie den folgenden Teams PowerShell-Befehl aus, um zu überprüfen, ob die lokale Nummer entfernt und die Änderungen von der lokalen Version mit Microsoft 365 synchronisiert wurden:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

Nachdem die Änderungen mit dem Microsoft 365 Online-Verzeichnis synchronisiert wurden, lautet die erwartete Ausgabe:

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

Um zu überprüfen, ob die Telefonnummer entfernt wurde, führen Sie den folgenden Teams PowerShell-Befehl aus:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> Wie lange es dauert, bis die Entfernung wirksam wird, hängt von Ihrer Konfiguration ab. Das Entfernen der Telefonnummer kann bis zu 10 Minuten dauern, in seltenen Fällen kann es bis zu 24 Stunden dauern. 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>Entfernen der Online-VoIP-Routingrichtlinie, die Ihrem Benutzer zugeordnet ist

Nachdem die Nummer nicht zugewiesen wurde, entfernen Sie die Dem Benutzer zugeordnete Online-VoIP-Routingrichtlinie, indem Sie den folgenden Teams PowerShell-Befehl ausführen:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>Beziehen von Telefonnummern

Wenden Sie sich an Ihren Betreiber, um Ihre Telefonnummern zu Telefonieanbieter mit Mobil in einem berechtigten, simfähigen Wlan-VoIP-Plan zu portieren.

Nachdem Ihr Betreiber die Bestellung abgeschlossen hat, werden Nummern in Ihren Mandanten hochgeladen. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. 

#### <a name="assign-phone-numbers"></a>Zuweisen von Telefonnummern

Sie können Benutzer mithilfe des Teams Admin Centers oder mithilfe von PowerShell Operator Connect-Nummern zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](assign-change-or-remove-a-phone-number-for-a-user.md).


## <a name="manage-your-operators"></a>Anbieter verwalten

Auf der Registerkarte **"Meine Operatoren** " können Sie Ihre Operatoren und deren Status anzeigen und die folgenden Änderungen an Ihrer Auswahl vornehmen:  

- Anbieterdienste nach Land verwalten
- Einen Anbieter anhalten
- Einen Anbieter entfernen

> [!NOTE]
> Bevor Sie einen Anbieter aus Ihrer Organisation oder aus einem Land entfernen, müssen Sie alle Telefonnummern entfernen, die Benutzern in der Organisation oder dem Land zugewiesen sind, und den Anbieter kontaktieren, um die Nummern freizugeben.

## <a name="release-numbers"></a>Freigabenummern

Um Telefonnummern aus dem Teams Admin Center freizugeben, wechseln Sie zur Seite **"Telefonnummern** ", und wählen Sie eine Nummer aus.

- Wenn die Telefonnummer keinem Benutzer zugewiesen ist, wählen Sie **"Freigeben"** aus.

- Wenn die Telefonnummer einem Benutzer zugewiesen ist, müssen Sie die Zuweisung aufheben. Wählen Sie **"Bearbeiten"** und dann **"Benutzer entfernen" aus**. Nachdem Sie Ihre Änderungen gespeichert haben, wählen Sie **"Freigeben"** aus.

## <a name="manage-user-incoming-calling-policies"></a>Verwalten von Richtlinien für eingehende Benutzeranrufe

Sie können die Richtlinien für eingehende Anrufe eines Benutzers mithilfe des Teams Admin Centers oder mithilfe von PowerShell verwalten. Standardmäßig klingeln eingehende Anrufe für Telefonieanbieter mit Mobil Benutzer zuerst auf dem SIM-fähigen mobilen Gerät des Benutzers an die Teams-App. 

- Wenn die Einstellung für eingehende Anrufe eines Benutzers auf die Teams-App festgelegt ist, rufen alle eingehenden Anrufe die Teams-App auf dem SIM-fähigen Smartphone und alle anderen Teams-Endpunkte auf anderen Geräten gleichzeitig an. 

- Wenn die Einstellung für eingehende Anrufe eines Benutzers auf die systemeigene Wählhilfe festgelegt ist, klingeln alle eingehenden Anrufe an die systemeigene Wählhilfe auf dem SIM-fähigen Smartphone und klingeln gleichzeitig alle anderen Teams-Endpunkte auf anderen Geräten. 

### <a name="use-the-teams-admin-center"></a>Verwenden des Teams Admin Centers

So verwalten Sie die Richtlinien für eingehende Anrufe eines Benutzers mithilfe des Teams Admin Centers:

1. Wählen Sie auf der Registerkarte "VoIP" die Option **"Mobilitätsrichtlinien" aus**. 

2. Klicken Sie auf "Hinzufügen", um eine neue mobile Richtlinie **hinzuzufügen**.

3. Wählen Sie einen Namen aus, fügen Sie eine Beschreibung der Richtlinie hinzu, und wählen Sie in der Dropdownoption " **Wählen Sie eine mobile Wählhilfe" eine** der folgenden Optionen aus:

   -  **Microsoft Teams** , um die Teams-App zuerst auf dem SIM-fähigen Smartphone anzuschalten. 

   - **Native Dialer** , um zuerst die systemeigene Wählhilfe auf dem SIM-fähigen Smartphone anzuschalten.

4. Weisen Sie die Richtlinien Benutzern zu. Siehe [Zuweisen von Richtlinien](assign-policies-users-and-groups.md).


### <a name="use-powershell"></a>Verwenden von PowerShell

1. Stellen Sie eine Verbindung mit Ihrem Mandanten her: Connect-MicrosoftTeams.
 
2. Erstellen Sie Richtlinien für eingehende Anrufe, um zuerst entweder die native Wählhilfe oder die Teams-App anzurufen. (Sie können den Richtliniennamen auswählen. In diesem Beispiel werden TeamsFirst und NativeFirst verwendet.) 

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. Gewähren von Richtlinien für Benutzer: 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. Benutzerrichtlinien überprüfen: 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. Alle Mobilitätsrichtlinienoptionen überprüfen: 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








