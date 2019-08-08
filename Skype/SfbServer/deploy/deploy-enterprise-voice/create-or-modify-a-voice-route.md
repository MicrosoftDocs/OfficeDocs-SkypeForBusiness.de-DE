---
title: Erstellen oder Ändern einer VoIP-Route in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine VoIP-Route in Skype for Business Server mithilfe des Skype for Business Server-Control Panels erstellen oder ändern.'
ms.openlocfilehash: e5b8fcb5617d1f5abcbbda0826c3366ab4f73cd8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233343"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Erstellen oder Ändern einer VoIP-Route in Skype for Business
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie eine VoIP-Route in Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung erstellen oder ändern.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>So erstellen Sie eine VoIP-Route mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf **Route**.
    
5. Klicken Sie auf **Neu**, um das Dialogfeld **Neue VoIP-Route** anzuzeigen.
    
6. Geben Sie in **Name** einen beschreibenden Namen für die VoIP-Route ein.
    
7. (Optional) Geben Sie in **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.
    
8. Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Zu suchendes Muster erstellen** verwenden, um einen regulären Ausdruck zu generieren oder Sie erstellen manuell einen regulären Ausdruck.
    
   - Geben Sie bei Verwendung des Tools **Zu suchendes Muster erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise + 425 ein, und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen**: Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein, die nicht für diese Route *geeignet* sein sollen. Wenn Sie beispielsweise Zahlen, die mit + 425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld **Ausnahmen** den Wert + 425237 ein, und klicken Sie dann auf **OK**.
    
   - Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter ["reguläre Ausdrücke von .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine **Alternative Rufnummern** Anzeige angeben, die auf der Anzeige der Rufnummernanzeige des Empfängers angezeigt wird.
    
10. Klicken Sie auf **Hinzufügen**, um der VoIP-Route einen oder mehrere Trunks zuzuordnen und wählen Sie aus der Liste einen Trunk aus.
    
11. Wenn Sie der VoIP-Route eine oder mehrere PSTN-Verwendungen zuordnen möchten, klicken Sie auf **Auswählen** und wählen Sie einen Eintrag aus der Liste der PSTN-Verwendungseinträge aus, die für Ihre Enterprise-VoIP-Bereitstellung definiert wurden.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Nutzungsdatensätze finden Sie unter [Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business](view-pstn-usage-records.md). > zum Erstellen oder Bearbeiten von PSTN-Nutzungsdaten Sätzen finden Sie unter [erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md) .
  
12. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Namen des Datensatzes, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    > [!NOTE]
    > Im Gegensatz zu einer VoIP-Richtlinie, bei der die Reihenfolge der PSTN-Verwendungseinträge eine wichtige Rolle spielt, ist die Reihenfolge der PSTN-Verwendungseinträge in einer VoIP-Route unerheblich. Dennoch wird empfohlen, die Liste nach Verwendungshäufigkeit zu strukturieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
13. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein** einen Wert ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
14. Klicken Sie auf **OK**, um die VoIP-Route zu speichern.
    
    > [!IMPORTANT]
    > Jedes Mal, wenn Sie eine VoIP-Route erstellen, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>So ändern Sie eine VoIP-Route

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und klicken Sie dann auf **Route**.
    
3. Verwenden Sie auf der Seite **Route** eine der folgenden Methoden, um eine VoIP-Route zu ändern:
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten**, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Klicken Sie auf die neue Kopie der VoIP-Route, die Sie soeben erstellt haben, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
4. Geben Sie auf der Seite **VoIP-Route bearbeiten** im Feld **Name** einen beschreibenden Namen für die VoIP-Route ein.
    
5. (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.
    
6. Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Muster für Vergleich erstellen** verwenden, um einen regulären Ausdruck zu generieren, oder Sie erstellen manuell einen regulären Ausdruck.
    
   - Geben Sie bei Verwendung des Tools **Zu suchendes Muster erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise +425 ein und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen**: Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein, die nicht für diese Route *geeignet* sein sollen. Wenn Sie beispielsweise Zahlen, die mit + 425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld **Ausnahmen** den Wert + 425237 ein, und klicken Sie dann auf **OK**.
    
   - Wenn Sie das Übereinstimmungsmuster manuell definieren möchten, klicken Sie in dem Tool **Muster zum Anpassen erstellen** auf **Bearbeiten** , und geben Sie dann einen regulären .NET Framework-Ausdruck ein, um das Übereinstimmungsmuster für die Zielrufnummern anzugeben, auf die die Route angewendet wird. Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter ["reguläre Ausdrücke von .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine **Alternative Rufnummern** Anzeige angeben, die auf der Anzeige der Rufnummernanzeige des Empfängers angezeigt wird.
    
8. Klicken Sie auf **Hinzufügen**, um der VoIP-Route einen oder mehrere PSTN-Trunks (Public Switched Telephone Network Telefonfestnetz) zuzuordnen und wählen Sie aus der Liste einen Trunk aus.
    
9. Klicken Sie auf **auswählen** , und wählen Sie einen Eintrag aus der Liste der PSTN-Nutzungsdatensätze aus, die für Ihre Enterprise-VoIP-Bereitstellung definiert wurden, um eine oder mehrere PSTN-Nutzungen der VoIP-Route zuzuordnen.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Nutzungsdatensätze finden Sie unter [Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business](view-pstn-usage-records.md). > zum Erstellen oder Bearbeiten von PSTN-Nutzungsdaten Sätzen finden Sie unter [erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md). 
  
10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Namen des Datensatzes, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    > [!NOTE]
    > Im Gegensatz zu einer VoIP-Richtlinie, in der die Reihenfolge, in der die Einträge für PSTN-Nutzung aufgelistet sind, wichtig ist, ist die Reihenfolge der PSTN-Nutzungsdatensätze in einer VoIP-Route bedeutungslos. Es wird jedoch empfohlen, die Liste nach Häufigkeit der Verwendung zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
11. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein** einen Wert ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
12. Klicken Sie auf **OK**.
    
13. Klicken Sie auf der Seite **Route** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**. 
    
    > [!NOTE]
    > Bei jeder Erstellung oder Änderung einer VoIP-Route müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business](view-pstn-usage-records.md)
  
[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)

