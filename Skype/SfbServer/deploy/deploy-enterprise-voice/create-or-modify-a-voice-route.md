---
title: Erstellen oder Ändern einer VoIP-Route in Skype für Unternehmen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Zusammenfassung: Informationen Sie zum Erstellen oder Ändern einer VoIP-Route in Skype für Business Server mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: 166b9635d9ddb50ec65b7cbc4d55aa92c19b55e0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888570"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Erstellen oder Ändern einer VoIP-Route in Skype für Unternehmen
 
**Zusammenfassung:** Informationen Sie zum Erstellen oder Ändern einer VoIP-Route in Skype für Business Server mithilfe der Skype für Business Server-Systemsteuerung.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Erstellen Sie eine VoIP-Route mithilfe der Skype für Business Server-Systemsteuerung

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf **Route**.
    
5. Klicken Sie auf **Neu**, um das Dialogfeld **Neue VoIP-Route** anzuzeigen.
    
6. Geben Sie in **Name** einen beschreibenden Namen für die VoIP-Route ein.
    
7. (Optional) Geben Sie in **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.
    
8. Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Zu suchendes Muster erstellen** verwenden, um einen regulären Ausdruck zu generieren oder Sie erstellen manuell einen regulären Ausdruck.
    
   - Geben Sie bei Verwendung des Tools **Zu suchendes Muster erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie zum Beispiel +425, und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen**: Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die Übereinstimmung, die Sie Patterns *Not* möchten dies Weiterleitung an die aufzunehmen. Beispielsweise um Zahlen, beginnend mit +425237 aus der Route enthalten sein sollen, geben Sie einen Wert von + 425237 im Feld **Ausnahmen** , und klicken Sie dann auf **OK**.
    
   - Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Ausführliche Informationen zum Schreiben von regulärer Ausdrücken finden Sie unter ["reguläre Ausdrücke von .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine **Alternative Anrufer-ID** angeben, die in der Aufgabenliste des Empfängers Anrufer ID Anzeige angezeigt wird.
    
10. Klicken Sie auf **Hinzufügen**, um der VoIP-Route einen oder mehrere Trunks zuzuordnen und wählen Sie aus der Liste einen Trunk aus.
    
11. Wenn Sie der VoIP-Route eine oder mehrere PSTN-Verwendungen zuordnen möchten, klicken Sie auf **Auswählen** und wählen Sie einen Eintrag aus der Liste der PSTN-Verwendungseinträge aus, die für Ihre Enterprise-VoIP-Bereitstellung definiert wurden.
    
    > [!NOTE]
    > Zum Anzeigen der Eigenschaften aller verfügbaren PSTN-verwendungsdatensätzen finden Sie unter [View PSTN-Verwendungseinträge in Skype für Unternehmen](view-pstn-usage-records.md). > zum Erstellen oder Bearbeiten von PSTN-verwendungsdatensätzen finden Sie unter [Erstellen oder ändern eine VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Business](voice-policy-and-pstn-usage-records.md)
  
12. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um einen Datensatz Position in der Liste zu ändern, markieren Sie den Namen des Datensatzes, und klicken Sie auf den Pfeil nach oben oder nach-unten Sie-Pfeil.
    
    > [!NOTE]
    > Im Gegensatz zu einer VoIP-Richtlinie, bei der die Reihenfolge der PSTN-Verwendungseinträge eine wichtige Rolle spielt, ist die Reihenfolge der PSTN-Verwendungseinträge in einer VoIP-Route unerheblich. Dennoch wird empfohlen, die Liste nach Verwendungshäufigkeit zu strukturieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype für Business Server durchläuft die Liste von oben nach unten.) 
  
13. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein** einen Wert ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
14. Klicken Sie auf **OK**, um die VoIP-Route zu speichern.
    
    > [!IMPORTANT]
    > Jedes Mal, wenn Sie eine VoIP-Route erstellen, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>So ändern Sie eine VoIP-Route

1. Öffnen von Skype Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und klicken Sie dann auf **Route**.
    
3. Verwenden Sie auf der Seite **Route** eine der folgenden Methoden, um eine VoIP-Route zu ändern:
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten**, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Klicken Sie auf die neue Kopie der VoIP-Route, die Sie soeben erstellt haben, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
4. Geben Sie auf der Seite **VoIP-Route bearbeiten** im Feld **Name** einen beschreibenden Namen für die VoIP-Route ein.
    
5. (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.
    
6. Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Muster für Vergleich erstellen** verwenden, um einen regulären Ausdruck zu generieren, oder Sie erstellen manuell einen regulären Ausdruck.
    
   - Geben Sie bei Verwendung des Tools **Zu suchendes Muster erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise +425 ein und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen**: Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die Übereinstimmung, die Sie Patterns *Not* möchten dies Weiterleitung an die aufzunehmen. Beispielsweise um Zahlen, beginnend mit +425237 aus der Route enthalten sein sollen, geben Sie einen Wert von + 425237 im Feld **Ausnahmen** , und klicken Sie dann auf **OK**.
    
   - Um das Vergleichsmuster manuell zu definieren, klicken Sie auf **Bearbeiten** , in dem Tool **erstellen ein Muster an** , und geben Sie in einem regulären .NET Framework-Ausdruck, um das Vergleichsmuster für Zielrufnummern anzugeben, dem die Route angewendet wird. Ausführliche Informationen zum Schreiben von regulärer Ausdrücken finden Sie unter ["reguläre Ausdrücke von .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine **Alternative Anrufer-ID** angeben, die in der Aufgabenliste des Empfängers Anrufer ID Anzeige angezeigt wird.
    
8. Klicken Sie auf **Hinzufügen**, um der VoIP-Route einen oder mehrere PSTN-Trunks (Public Switched Telephone Network Telefonfestnetz) zuzuordnen und wählen Sie aus der Liste einen Trunk aus.
    
9. Um die VoIP-Route einen oder mehrere PSTN-Verwendungen zuzuordnen, klicken Sie auf **auswählen** , und wählen Sie einen Eintrag aus der Liste der PSTN-verwendungsdatensätzen, die für die Enterprise-VoIP-Bereitstellung definiert wurden.
    
    > [!NOTE]
    > Zum Anzeigen der Eigenschaften aller verfügbaren PSTN-verwendungsdatensätzen finden Sie unter [View PSTN-Verwendungseinträge in Skype für Unternehmen](view-pstn-usage-records.md). > zum Erstellen oder Bearbeiten von PSTN-verwendungsdatensätzen finden Sie unter [Erstellen oder ändern eine VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Business](voice-policy-and-pstn-usage-records.md). 
  
10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um einen Datensatz Position in der Liste zu ändern, markieren Sie den Namen des Datensatzes, und klicken Sie auf den Pfeil nach oben oder nach-unten Sie-Pfeil.
    
    > [!NOTE]
    > Im Gegensatz zu einer VoIP-Richtlinie, in die Reihenfolge, in welche, die PSTN-Verwendungseinträge aufgelisteten, wichtig ist, wirkt sich die Reihenfolge der PSTN-verwendungsdatensätzen in eine VoIP-Route. Wird jedoch empfohlen, dass Sie die Liste beispielsweise nach der Häufigkeit der Verwendung, organisieren: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype für Business Server durchläuft die Liste von oben nach unten.) 
  
11. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein** einen Wert ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
12. Klicken Sie auf **OK**.
    
13. Klicken Sie auf der Seite **Route** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**. 
    
    > [!NOTE]
    > Bei jeder Erstellung oder Änderung einer VoIP-Route müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Verwendungseinträge in Skype für Unternehmen](view-pstn-usage-records.md)
  
[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen](voice-policy-and-pstn-usage-records.md)
  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md)

