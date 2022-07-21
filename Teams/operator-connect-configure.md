---
title: Konfigurieren von Telefonieanbieter
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
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie Näheres über das Konfigurieren von Telefonieanbieter.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9a773e7c8767164480374826a2410050681505a
ms.sourcegitcommit: 5a8a077b30a0eab2342afc422869adaa682a015b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2022
ms.locfileid: "66915193"
---
# <a name="configure-operator-connect"></a>Konfigurieren von Telefonieanbieter

In diesem Artikel wird beschrieben, wie diese Einstellungen konfiguriert werden. Lesen Sie vor dem Konfigurieren von Telefonieanbieter [Planen für Telefonieanbieter](operator-connect-plan.md), um sich über Voraussetzungen und Lizenzierung zu informieren.

## <a name="enable-an-operator"></a>Einen Anbieter aktivieren

Sie können Operatoren im Teams Admin Center aktivieren, bearbeiten und entfernen. Navigieren Sie im linken Navigationsbereich zu **Voice > Anbieter**.

So aktivieren Sie einen Anbieter:

1. **Wählen Sie einen Anbieter aus.** Filtern Sie auf der Registerkarte **Alle Anbieter** verfügbare Anbieter nach Region oder Dienst, um den geeigneten Anbieter für Ihre Anrufanforderungen zu finden. Wählen Sie dann den Anbieter aus, den Sie aktivieren möchten.  

2. **Wählen Sie Länder aus.** Wählen Sie unter **Anbietereinstellungen** die Länder aus, die Sie mit dem ausgewählten Anbieter aktivieren möchten.

3. **Bereitstellen von Kontaktinformationen** Ihre Kontaktinformationen, einschließlich Ihres vollständigen Namens und Ihrer E-Mail-Adresse, werden automatisch an Ihren Betreiber weitergegeben. Sie können diese Informationen später ändern. Darüber hinaus müssen Sie die Unternehmensgröße angeben, und Sie haben die Möglichkeit, Ihre Telefonnummer anzugeben. Operatoren verwenden diese Informationen, um Sie mit weiteren Details zu Operator Connect zu kontaktieren.

4. Stimmen Sie dem Hinweis zur Datenübertragung zu.

5. **Fügen Sie Ihren Anbieter hinzu.** Klicken Sie zum Speichern auf **Als meinen Anbieter hinzufügen**.

## <a name="set-up-phone-numbers"></a>Telefonnummern einrichten

Wie Telefonnummern eingerichtet werden, hängt davon ab, ob Sie Nummern für neue Benutzer einrichten oder vorhandene Nummern aus Microsoft-Anrufplänen oder Direct Routing verschieben möchten.

- Wenn Sie Telefonnummern für neue Benutzer beziehen müssen, lesen Sie [Beziehen von Nummern für neue Microsoft Teams-Benutzer](#acquire-numbers-for-new-teams-users).

- Wenn Sie vorhandene Nummern aus Anrufplänen zu Telefonieanbieter verschieben möchten, lesen Sie [Verschieben von Nummern aus Anrufplänen zu Telefonieanbieter](#move-numbers-from-calling-plans-to-operator-connect).

- Wenn Sie vorhandene Nummern von Direct Routing zu Telefonieanbieter verschieben möchten, lesen Sie [Verschieben von Nummern von Direct Routing zu Telefonieanbieter](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Telefonnummern für neue Microsoft Teams-Benutzer beziehen

Führen Sie die folgenden Schritte aus, um Nummern für neue Microsoft Teams-Benutzer zu erhalten:

1. **Weisen Sie eine Telefonsystem-Lizenz zu.** Sie können Ihren Benutzern über das Microsoft 365 Admin Center oder mithilfe von PowerShell eine Telefonsystemlizenz zuweisen. Weitere Informationen finden Sie unter [Benutzern Microsoft Teams-Add-On-Lizenzen zuweisen](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Benutzer, denen Telefonnummern zugewiesen werden, die mit Operator Connect erworben werden, müssen sich im TeamsOnly-Modus befinden. Wenn sich Ihre Organisation im TeamsOnly-Modus befindet, befinden sich alle Ihre Benutzer im TeamsOnly-Modus. Um dies zu überprüfen, wechseln Sie im Teams Admin Center zu **Teams > Teams-Upgradeeinstellungen**. Wenn sich Ihre Organisation im Inselmodus befindet, überprüfen Sie, ob sich bestimmte Benutzer im TeamsOnly-Modus befinden. Wechseln **Sie zu "Benutzer"** , und wählen Sie ein Benutzerkonto aus. Auf der Registerkarte **"Konto"** unter " **Teams-Upgrade** " sollte der Koexistenzmodus auf "TeamsOnly" festgelegt sein.

3. **Beziehen Sie Telefonnummern.** Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Eine Liste der Betreiberwebsites finden Sie im [Verzeichnis "Microsoft 365 Operator Connect"](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

4. **Weisen Sie Nummern zu.** Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Nummern aus dem Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

> [!NOTE]
> Zusätzlich zum [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md) können Sie gebührenpflichtige oder gebührenfreie Telefonnummern für Dienste wie Audiokonferenzen (für Konferenzbrücken), automatische Telefonzentralen und Anrufwarteschleifen (auch als Servicenummern bezeichnet) erhalten. Im Vergleich zu Telefonnummern für Benutzer oder Abonnenten haben Leistungsnummern eine höhere Kapazität für gleichzeitige Anrufe. Beispielsweise kann eine Dienstnummer Hunderte von Anrufen gleichzeitig verarbeiten, während die Telefonnummer eines Benutzers nur wenige Anrufe gleichzeitig verarbeiten kann. Um Servicenummern zu erhalten, wenden Sie sich an Ihren Betreiber.

### <a name="emergency-addresses"></a>Notfalladressen

Die Notfalladresse ist ein statischer Ort, der einer Nummer zugeordnet ist. Nachdem Sie Notfalladressen im Teams Admin Center erstellt haben, hängt es von Ihrem Operator ab, wie Sie die Adressen zuweisen oder später ändern.

Um Notfalladressen Nummern zuzuweisen, implementiert Ihr Operator eines von drei Szenarien:

- Der Operator weist den Telefonnummern Notfalladressen zu und ermöglicht Es Ihnen, diese später im Teams Admin Center zu ändern.

- Der Operator weist keine Adressen zu und ermöglicht Es Ihnen, den Telefonnummern im Teams Admin Center Notfalladressen zuzuweisen.

- Der Operator weist den Telefonnummern Notfalladressen zu und lässt keine Änderung zu. In diesem Szenario müssen Sie sich an Ihren Betreiber wenden, um Änderungen an Telefonnummern und deren zugewiesener Notfalladresse vorzunehmen.

Weitere Informationen zu Notrufen finden [Sie unter Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md) und [Planen und Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Telefonnummern aus Anrufplänen zu Telefonieanbieter verschieben

1. Wenden Sie sich an Ihren Anbieter, um Ihre Nummern zu Telefonieanbieter zu portieren. Lesen Sie das [Microsoft 365 Operator Connect-Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) , um die Website Ihres Betreibers zu finden.

2. Nachdem Der Betreiber den Portierungsauftrag abgeschlossen hat, lädt der Betreiber die Nummern in Ihren Mandanten hoch.

3. Weisen Sie Benutzern Telefonieanbieter-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Telefonnummern von Direct Routing zu Telefonieanbieter verschieben

Führen Sie die folgenden Schritte aus, um von Direct Routing zu Operator Connect mit lokalen oder Onlinetelefonnummern zu wechseln:

#### <a name="step-1---identify-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Schritt 1: Ermitteln, ob die vorhandenen Direct Routing-Nummern online oder lokal zugewiesen werden.

Überprüfen Sie, ob dem Benutzer eine Direct Routing-Nummer zugewiesen ist, indem Sie den Befehl "Teams PowerShell-Modul" ausführen:

```PowerShell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
```

Überprüfen Sie, ob `NumberType` directRouting ist.

Wie Sie Ihre vorhandenen Direct Routing-Nummern entfernen, hängt davon ab, ob die Nummer lokal oder online zugewiesen ist. Führen Sie zum Überprüfen den folgenden Teams PowerShell-Modulbefehl aus:
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

Wenn `OnPremLineUri` eine E.164-Telefonnummer vorhanden ist, wurde die Telefonnummer lokal zugewiesen und mit Microsoft 365 synchronisiert.

**Um vorhandene Direct Routing-Nummern zu migrieren, die online zu Operator Connect zugewiesen sind**, wenden Sie sich an Ihren Betreiber. Informationen zur Website Ihres Betreibers finden Sie im [Microsoft 365 Operator Connect-Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Am vereinbarten Datum und der vereinbarten Uhrzeit migriert Ihr Betreiber Ihre Nummern von Direct Routing zu Operator Connect.

Führen Sie zum **Migrieren von lokalen Direct Routing-Nummern zu Operator Connect** den folgenden powerShell-Befehl Skype for Business Server aus:
>[!IMPORTANT]
> Die Telefonnummer ist während der Migration nicht mehr verfügbar. Stimmen Sie sich daher vor Beginn mit Ihrem Operator Connect-Operator ab.

```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

Wie lange es dauert, bis die Entfernung wirksam wird, hängt von Ihrer Konfiguration ab. Um zu überprüfen, ob die lokale Nummer entfernt wurde und die Änderungen von lokal mit Microsoft 365 synchronisiert wurden, führen Sie den folgenden Teams PowerShell-Modulbefehl aus: 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
Nachdem die Änderungen mit dem Microsoft 365 Online-Verzeichnis synchronisiert wurden, lautet die erwartete Ausgabe: 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```




```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

Das Entfernen der Telefonnummer kann bis zu 10 Minuten dauern. In seltenen Fällen kann es bis zu 24 Stunden dauern. Um zu überprüfen, ob die Telefonnummer entfernt wurde, führen Sie den folgenden Teams PowerShell-Modulbefehl aus: 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Schritt 2: Entfernen der Online-VoIP-Routingrichtlinie, die Ihrem Benutzer zugeordnet ist

Nachdem die Nummer nicht zugewiesen wurde, entfernen Sie die Dem Benutzer zugeordnete Online-VoIP-Routingrichtlinie, indem Sie den folgenden Teams PowerShell-Modulbefehl ausführen:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Schritt 3 : Erwerben von Telefonnummern

Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Informationen zur Website Ihrer Betreiber finden Sie im [Microsoft 365 Operator Connect-Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

#### <a name="step-4---assign-phone-numbers"></a>Schritt 4 : Zuweisen von Telefonnummern

Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Telefonieanbieter-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

### <a name="assign-numbers"></a>Telefonnummern zuweisen

Informationen zum Zuweisen von Telefonnummern zu Ihren Benutzern finden Sie unter [Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](assign-change-or-remove-a-phone-number-for-a-user.md).

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

## <a name="related-topics"></a>Verwandte Themen

- [Planen von automatischen Telefonzentralen und Anrufwarteschleifen in Microsoft Teams](plan-auto-attendant-call-queue.md)
