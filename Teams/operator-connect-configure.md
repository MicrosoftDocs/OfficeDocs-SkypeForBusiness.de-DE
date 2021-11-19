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
ms.openlocfilehash: 2fa7a7c314fe2d31e5306ec96902f8ca87e44355
ms.sourcegitcommit: 5c88a07f07f9faad294d614d507e43173efc5f46
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111965"
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

2. Benutzer, denen Telefonnummern zugewiesen werden, die über die Operator-Verbinden müssen sich im TeamsOnly-Modus befinden. Wenn Ihre Organisation im TeamsOnly-Modus ist, befinden sich alle Ihre Benutzer im TeamsOnly-Modus. Um dies zu überprüfen, wechseln Teams Admin Center zu **Teams > Teams Upgradeeinstellungen**. Wenn sich Ihre Organisation im Islands-Modus befindet, überprüfen Sie, ob sich bestimmte Benutzer imOnly-Modus befinden. Wechseln Sie zu **Benutzer,** und wählen Sie ein Benutzerkonto aus. Auf der **Registerkarte** Konto sollte Teams Koexistenzmodus auf "TeamsOnly" festgelegt sein. 

3. **Beziehen Sie Telefonnummern.** Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Eine Liste der Operatorwebsites finden Sie im Verzeichnis [Microsoft 365 Operator Verbinden](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

4. **Weisen Sie Nummern zu.** Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Nummern über das Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

> [!NOTE]
> Sie können [](getting-phone-numbers-for-your-users.md)nicht nur Telefonnummern für Ihre Benutzer erhalten, sondern auch gebührenpflichtige oder gebührenfreie Telefonnummern für Dienste wie Audiokonferenzen (für Konferenzbrücken), automatische Telefonkonferenzen und Anrufwarteschleifen (auch als Servicenummern bezeichnet). Im Vergleich zu Telefonnummern für Benutzer oder Abonnenten haben Leistungsnummern eine höhere Kapazität für gleichzeitige Anrufe. So kann eine Leistungsnummer beispielsweise Hunderte von Anrufen gleichzeitig verarbeiten, während die Telefonnummer eines Benutzers nur einige wenige Anrufe gleichzeitig verarbeiten kann. Wenden Sie sich an Ihren Netzbetreiber, um Servicenummern zu erhalten.

### <a name="emergency-addresses"></a>Notfalladressen

Die Notfalladresse ist ein statischer Standort, der einer Nummer zugeordnet ist. Nachdem Sie im Teams Admin Center Notfalladressen erstellt haben, hängt die Art und Weise, wie Sie die Adressen zuweisen oder später ändern, von Ihrem Anbieter ab.

Zum Zuweisen von Nummern zu Notfalladressen implementiert Ihr Netzbetreiber eines von drei Szenarien:

- Der Netzbetreiber weist den Telefonnummern Notfalladressen zu und ermöglicht Ihnen, diese später im Teams Admin Center zu ändern.

- Der Netzbetreiber weist keine Adressen zu und ermöglicht Ihnen, den Telefonnummern im Teams Notfalladressen zuzuordnen.

- Der Netzbetreiber weist den Telefonnummern Notfalladressen zu und lässt keine Änderung zu. In diesem Szenario müssen Sie sich an Ihren Netzbetreiber wenden, um Änderungen an den Telefonnummern und der zugewiesenen Notfalladresse vorzunehmen.

Weitere Informationen zu Notrufen finden Sie unter Verwalten von [Notrufen](what-are-emergency-locations-addresses-and-call-routing.md) und [Planen und Konfigurieren dynamischer Notrufe.](configure-dynamic-emergency-calling.md)

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Telefonnummern aus Anrufplänen zu Telefonieanbieter verschieben

1. Wenden Sie sich an Ihren Anbieter, um Ihre Nummern zu Telefonieanbieter zu portieren. Informationen [Microsoft 365 Der Verbinden finden](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Sie auf der Website Ihres Anbieters.

2. Nachdem Ihr Anbieter den Portierungsauftrag abgeschlossen hat, können Sie die Zuweisung von Anrufplan-Telefonnummern Ihrer Benutzer aufheben und die Anrufplanlizenz entfernen. Anschließend kann Ihr Anbieter die Nummern in Ihren Mandanten hochladen.

3. Weisen Sie Benutzern Telefonieanbieter-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Telefonnummern von Direct Routing zu Telefonieanbieter verschieben

1. Entfernen Sie die vorhandene Telefonnummer von einem Benutzer wie folgt:  

   Rufen Sie den bestehenden lokalen Anschluss-URI ab, indem Sie den folgenden PowerShell-Befehl ausführen:

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   Entfernen Sie den bestehenden lokalen Anschluss-URI, indem Sie den folgenden PowerShell-Befehl ausführen:  

   ```
   Set-CsUser -Identity <user> -OnPremLineURI $null 
   ```

2. Entfernen Sie alle PSTNUsage-Elemente, die Ihren Benutzern zugeordnet sind. Andernfalls werden Anrufe an das Gateway weitergeleitet, das in PSTNUsage angegeben ist. Informationen zum Entfernen von PSTNUsage finden Sie unter [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).

3. Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Informationen zum Auf der Website der Operatoren finden Sie im Microsoft 365 [Operator Verbinden Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen Sie [Suchen Ihrer Microsoft 365 Mandanten-ID](/onedrive/find-your-office-365-tenant-id).

4. Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen. Weisen Sie Benutzern Telefonieanbieter-Nummern über das Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter [Zuweisen von Telefonnummern](#assign-numbers).

### <a name="assign-numbers"></a>Telefonnummern zuweisen

Informationen zum Zuweisen von Telefonnummern zu Ihren Benutzern finden Sie unter Zuweisen, Ändern oder Entfernen einer Telefonnummer [für einen Benutzer.](assign-change-or-remove-a-phone-number-for-a-user.md)

## <a name="manage-your-operators"></a>Anbieter verwalten

Auf der **Registerkarte Meine Operatoren** können Sie die Operatoren und deren Status anzeigen und die folgenden Änderungen an Ihrer Auswahl vornehmen:  

- Anbieterdienste nach Land verwalten
- Einen Anbieter anhalten
- Einen Anbieter entfernen

> [!NOTE]
> Bevor Sie einen Anbieter aus Ihrer Organisation oder aus einem Land entfernen, müssen Sie alle Telefonnummern entfernen, die Benutzern in der Organisation oder dem Land zugewiesen sind, und den Anbieter kontaktieren, um die Nummern freizugeben.

## <a name="release-numbers"></a>Veröffentlichungsnummern

Wenn Sie Telefonnummern aus dem Teams Admin Center  veröffentlichen möchten, wechseln Sie zur Seite Telefon Telefonnummern, und wählen Sie eine Nummer aus.

- Wenn die Telefonnummer keinem Benutzer zugewiesen ist, wählen Sie Release **aus.**

- Wenn die Telefonnummer einem Benutzer zugewiesen ist, müssen Sie die Nummer wieder zuweisen. Wählen **Sie Bearbeiten** und dann Benutzer entfernen **aus.** Nachdem Sie Ihre Änderungen gespeichert haben, wählen Sie **Release aus.**

## <a name="related-topics"></a>Verwandte Themen

- [Planen von automatischen Telefonzentralen und Anrufwarteschleifen in Microsoft Teams](plan-auto-attendant-call-queue.md)
