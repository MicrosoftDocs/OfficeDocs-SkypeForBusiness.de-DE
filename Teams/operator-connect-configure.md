---
title: Konfigurieren von Telefonieanbieter
author: cazawideh
ms.author: czawideh
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
---

# <a name="configure-operator-connect"></a>Konfigurieren von Telefonieanbieter

In diesem Artikel wird beschrieben, wie diese Einstellungen konfiguriert werden. Lesen Sie vor dem Konfigurieren von Telefonieanbieter [Planen für Telefonieanbieter](operator-connect-plan.md), um sich über Voraussetzungen und Lizenzierung zu informieren.

## <a name="enable-an-operator"></a>Einen Anbieter aktivieren

Sie können Operatoren im Admin Center Teams bearbeiten und entfernen. Navigieren Sie im linken Navigationsbereich zu **Voice > Anbieter**.

So aktivieren Sie einen Anbieter:

1. **Wählen Sie einen Anbieter aus.** Filtern Sie auf der Registerkarte **Alle Anbieter** verfügbare Anbieter nach Region oder Dienst, um den geeigneten Anbieter für Ihre Anrufanforderungen zu finden. Wählen Sie dann den Anbieter aus, den Sie aktivieren möchten.  

2. **Wählen Sie Länder aus.** Wählen Sie unter **Anbietereinstellungen** die Länder aus, die Sie mit dem ausgewählten Anbieter aktivieren möchten.

3. **Bereitstellen von Kontaktinformationen** Ihre Kontaktinformationen, einschließlich Ihres vollständigen Namens und Ihrer E-Mail-Adresse, werden automatisch an Ihren Netzbetreiber weitergegeben. Sie können diese Informationen später ändern. Darüber hinaus müssen Sie die Unternehmensgröße bereitstellen und können Ihre Telefonnummer bereitstellen. Operatoren verwenden diese Informationen, um Sie mit weiteren Details zu den Operatoren Verbinden.

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

2. Benutzer, denen Telefonnummern zugewiesen werden, die über die Operator-Verbinden müssen sich im TeamsOnly-Modus befinden. Wenn Ihre Organisation im TeamsOnly-Modus ist, befinden sich alle Ihre Benutzer im TeamsOnly-Modus. Um dies zu überprüfen, wechseln Teams Admin Center zu **Teams > Teams Upgradeeinstellungen**. Wenn sich Ihre Organisation im Islands-Modus befindet, überprüfen Sie, ob sich bestimmte Benutzer imOnly-Modus befinden. Wechseln Sie zu **Benutzer** , und wählen Sie ein Benutzerkonto aus. Auf der **Registerkarte** Konto **sollte Teams Koexistenzmodus** auf "TeamsOnly" festgelegt sein.

3. **Beziehen Sie Telefonnummern.** Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Eine Liste der Operatorwebsites finden Sie im Verzeichnis [Microsoft 365 Operator Verbinden Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

4. **Weisen Sie Nummern zu.** Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Nummern über das Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

> [!NOTE]
> Sie können nicht nur Telefonnummern für Ihre Benutzer  [erhalten, sondern](getting-phone-numbers-for-your-users.md) auch gebührenpflichtige oder gebührenfreie Telefonnummern für Dienste wie Audiokonferenzen (für Konferenzbrücken), automatische Telefonkonferenzen und Anrufwarteschleifen (auch als Servicenummern bezeichnet). Im Vergleich zu Telefonnummern für Benutzer oder Abonnenten haben Leistungsnummern eine höhere Kapazität für gleichzeitige Anrufe. So kann eine Leistungsnummer beispielsweise Hunderte von Anrufen gleichzeitig verarbeiten, während die Telefonnummer eines Benutzers nur einige wenige Anrufe gleichzeitig verarbeiten kann. Wenden Sie sich an Ihren Netzbetreiber, um Servicenummern zu erhalten.

### <a name="emergency-addresses"></a>Notfalladressen

Die Notfalladresse ist ein statischer Standort, der einer Nummer zugeordnet ist. Nachdem Sie im Teams Admin Center Notfalladressen erstellt haben, hängt die Art und Weise, wie Sie die Adressen zuweisen oder später ändern, von Ihrem Anbieter ab.

Zum Zuweisen von Nummern zu Notfalladressen implementiert Ihr Netzbetreiber eines von drei Szenarien:

- Der Netzbetreiber weist den Telefonnummern Notfalladressen zu und ermöglicht Ihnen, diese später im Teams Admin Center zu ändern.

- Der Netzbetreiber weist keine Adressen zu und ermöglicht Es Ihnen, den Telefonnummern im Teams Admin Center Notfalladressen zuzuordnen.

- Der Netzbetreiber weist den Telefonnummern Notfalladressen zu und lässt keine Änderung zu. In diesem Szenario müssen Sie sich an Ihren Netzbetreiber wenden, um Änderungen an den Telefonnummern und der zugewiesenen Notfalladresse vorzunehmen.

Weitere Informationen zu Notrufen finden Sie unter [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md) und [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Telefonnummern aus Anrufplänen zu Telefonieanbieter verschieben

1. Wenden Sie sich an Ihren Anbieter, um Ihre Nummern zu Telefonieanbieter zu portieren. Informationen [Microsoft 365 Website der Verbinden finden](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Sie unter Verzeichnis des Netzbetreibers.

2. Nachdem Ihr Anbieter den Portierungsauftrag abgeschlossen hat, können Sie die Zuweisung von Anrufplan-Telefonnummern Ihrer Benutzer aufheben und die Anrufplanlizenz entfernen. Anschließend kann Ihr Anbieter die Nummern in Ihren Mandanten hochladen.

3. Weisen Sie Benutzern Telefonieanbieter-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Telefonnummern von Direct Routing zu Telefonieanbieter verschieben

Um Nummern aus dem Direct-Routing zu Operator Verbinden zu verschieben, muss die vorhandene Direct Routing-Nummer, die von Ihrem Anbieter in Ihren Mandanten hochgeladen wurde, vom Benutzer entfernt werden, dem sie zugewiesen ist. Nachdem die Zahl zu Operator Verbinden wurde, können Sie die Nummer dem Benutzer erneut zuweisen. Führen Sie die folgenden Schritte aus, um Verbinden mit lokalen oder Online-Telefonnummern vom Direct Routing zum Operator-Telefonnetz zu wechseln:

>[!IMPORTANT]
> Da die Telefonnummer während der Migration nicht mehr verwendet wird, koordinieren Sie sie mit Verbinden Operator, bevor Sie beginnen.

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>Schritt 1: Entfernen vorhandener Direktroutingnummern.

Wie Sie Ihre vorhandenen Direktroutingnummern entfernen, hängt davon ab, ob die Nummer lokal oder online zugewiesen ist. Führen Sie zur Überprüfung den folgenden Befehl aus:
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```

Wenn `OnPremLineUriManuallySet` auf festgelegt `False` und `LineUri` mit einer E.164-Telefonnummer aufgefüllt wurde, wurde die Telefonnummer lokal zugewiesen und mit Office 365.
    
**Führen Sie den folgenden Befehl aus, um lokal zugewiesene Direct Routing-Nummern** zu entfernen:
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

Wie lange es dauert, bis das Entfernen wirksam wird, hängt von Ihrer Konfiguration ab. Um zu überprüfen, ob die lokale Nummer entfernt und die Änderungen synchronisiert wurden, führen Sie den folgenden PowerShell-Befehl aus: 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```
       
Nachdem die Änderungen mit Ihrem Office 365 synchronisiert wurden, wird die erwartete Ausgabe wie erwartet angezeigt: 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
 OnPremLineURIManuallySet             : True
 OnPremLineURI                        : 
LineURI                              : 
```

<br> **Führen Sie den folgenden PowerShell-Befehl aus, um vorhandene Online-Direct Routing-Nummern** online zu entfernen:


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

Das Entfernen der Telefonnummer kann bis zu 10 Minuten dauern. In seltenen Fällen kann dies bis zu 24 Stunden dauern. Um zu überprüfen, ob die lokale Nummer entfernt und die Änderungen synchronisiert wurden, führen Sie den folgenden PowerShell-Befehl aus: 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl Number
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Schritt 2 – Entfernen der Ihrem Benutzer zugeordneten Online-Voiceroutingrichtlinie

Nachdem die Nummer nicht mehr zugewiesen wurde, entfernen Sie die Ihrem Benutzer zugeordnete Online-Voiceroutingrichtlinie, indem Sie den folgenden PowerShell-Befehl ausführen:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Schritt 3 – Erwerben von Telefonnummern

Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Informationen zum Auf der Website ihrer Operatoren finden Sie [im Microsoft 365 operator Verbinden Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

#### <a name="step-4---assign-phone-numbers"></a>Schritt 4 – Zuweisen von Telefonnummern

Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Telefonieanbieter-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

### <a name="assign-numbers"></a>Telefonnummern zuweisen

Informationen zum Zuweisen von Telefonnummern zu Ihren Benutzern finden Sie unter [Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](assign-change-or-remove-a-phone-number-for-a-user.md).

## <a name="manage-your-operators"></a>Anbieter verwalten

Auf der **Registerkarte Meine Operatoren** können Sie die Operatoren und deren Status anzeigen und die folgenden Änderungen an Ihrer Auswahl vornehmen:  

- Anbieterdienste nach Land verwalten
- Einen Anbieter anhalten
- Einen Anbieter entfernen

> [!NOTE]
> Bevor Sie einen Anbieter aus Ihrer Organisation oder aus einem Land entfernen, müssen Sie alle Telefonnummern entfernen, die Benutzern in der Organisation oder dem Land zugewiesen sind, und den Anbieter kontaktieren, um die Nummern freizugeben.

## <a name="release-numbers"></a>Veröffentlichungsnummern

Wenn Sie Telefonnummern aus dem Teams Admin Center veröffentlichen möchten, wechseln Sie zur  Seite Telefon Telefonnummern, und wählen Sie eine Nummer aus.

- Wenn die Telefonnummer einem Benutzer nicht zugewiesen ist, wählen Sie Release **aus**.

- Wenn die Telefonnummer einem Benutzer zugewiesen ist, müssen Sie die Nummer wieder zuweisen. Wählen **Sie Bearbeiten** und dann **Benutzer entfernen aus**. Nachdem Sie Ihre Änderungen gespeichert haben, wählen Sie **Release aus**.

## <a name="related-topics"></a>Verwandte Themen

- [Planen von automatischen Telefonzentralen und Anrufwarteschleifen in Microsoft Teams](plan-auto-attendant-call-queue.md)
