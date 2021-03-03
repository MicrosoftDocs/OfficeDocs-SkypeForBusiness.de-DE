---
title: Erstellen oder Ändern einer Sprachroute in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Zusammenfassung: Informationen zum Erstellen oder Ändern einer Sprachroute in Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung.'
ms.openlocfilehash: c9f1a234bf8aeeb1bfeb05f1464a48eb0e964405
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820455"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Erstellen oder Ändern einer Sprachroute in Skype for Business
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine Sprachroute in Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung erstellen oder ändern.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>So erstellen Sie eine Sprachroute mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf **Route**.
    
5. Klicken Sie auf **Neu**, um das Dialogfeld **Neue VoIP-Route** anzuzeigen.
    
6. Geben **Sie im** Namen einen beschreibenden Namen für die Sprachroute ein.
    
7. (Optional) Geben **Sie in**"Beschreibung" zusätzliche beschreibende Informationen für die Sprachroute ein.
    
8. Um die Muster anzugeben, die diese Route aufnehmen  soll, können Sie entweder das Muster erstellen, um das Tool zum Generieren eines regulären Ausdrucks zu vervollständigen, oder den regulären Ausdruck manuell schreiben.
    
   - Geben Sie bei Verwendung des Tools **Muster für Vergleich erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise +425 ein, und klicken Sie dann auf **"Hinzufügen".** Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein, die  *diese*  Route nicht aufnehmen soll. Wenn Sie beispielsweise Nummern, die mit +425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld "Ausnahmen" den Wert +425237 ein, und klicken Sie dann auf **"OK".** 
    
   - Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Weitere Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine alternative **Anrufer-ID** angeben, die auf der Anzeige der Anrufer-ID des Empfängers angezeigt wird.
    
10. Klicken Sie auf "Hinzufügen", und  wählen Sie dann einen Trunk aus der Liste aus, um der Sprachroute einen oder mehrere Trunks zuzuordnen.
    
11. Klicken Sie auf "Auswählen", und wählen Sie einen Eintrag aus  der Liste der PSTN-Verwendungseinträge aus, die für Ihre Bereitstellung definiert wurden, um der Sprachroute eine oder mehrere Verwendungen des Telefonnetzes (Public Switched Telephone Network, PSTN) Enterprise-VoIP zuzuordnen.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdatensätze finden Sie unter Anzeigen von PSTN-Verwendungsdatensätzen [in Skype for Business.](view-pstn-usage-records.md) > Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter "Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen [in Skype for Business".](voice-policy-and-pstn-usage-records.md)
  
12. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.
    
    > [!NOTE]
    > Im Gegensatz zu einer Voicerichtlinie, bei der die Reihenfolge, in der die PstN-Verwendungseinträge aufgeführt werden, wichtig ist, ist die Reihenfolge, in der die PstN-Verwendungseinträge in der Sprachroute aufgelistet werden, unerheblich. Es wird jedoch empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
13. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
14. Klicken Sie auf **OK**, um die VoIP-Route zu speichern.
    
    > [!IMPORTANT]
    > Jedes Mal, wenn Sie eine Voiceroute erstellen, müssen Sie den Befehl **"Commit** für alle" ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business.](voice-route-config-changes.md) 
  
### <a name="to-modify-a-voice-route"></a>So ändern Sie eine VoIP-Route

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Route**.
    
3. Verwenden Sie auf der Seite **Route** eine der folgenden Methoden, um eine VoIP-Route zu ändern:
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten**, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Klicken Sie auf die neue Kopie der VoIP-Route, die Sie soeben erstellt haben, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
4. Geben Sie auf der Seite **VoIP-Route bearbeiten** im Feld **Name** einen beschreibenden Namen für die VoIP-Route ein.
    
5. (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.
    
6. Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Muster für Vergleich erstellen** verwenden, um einen regulären Ausdruck zu generieren, oder Sie erstellen manuell einen regulären Ausdruck.
    
   - Geben Sie bei Verwendung des Tools **Muster für Vergleich erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise +425 ein, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein, die  *diese*  Route nicht aufnehmen soll. Wenn Sie beispielsweise Nummern, die mit +425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld "Ausnahmen" den Wert +425237 ein, und klicken Sie dann auf **"OK".** 
    
   - Zum manuellen Definieren des  Vergleichsmusters klicken Sie im Tool "Muster zum Abgleichen erstellen" auf "Bearbeiten", und geben Sie dann einen regulären .NET Framework-Ausdruck ein, um das Vergleichsmuster für Zieltelefonnummern anzugeben, auf die die Route angewendet wird.  Weitere Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Wählen **Sie "Anrufer-ID** unterdrücken" aus, wenn sie dem Anrufempfänger nicht angezeigt werden soll. Wenn Sie diese Option auswählen, müssen Sie eine alternative **Anrufer-ID** angeben, die auf der Anzeige der Anrufer-ID des Empfängers angezeigt wird.
    
8. Klicken Sie auf "Hinzufügen", und wählen Sie dann einen Trunk aus der Liste aus, um der Sprachroute einen oder mehrere Trunks (Public Switched Telephone Network, PSTN) zuzuordnen.
    
9. Klicken Sie auf "Auswählen", und wählen  Sie einen Eintrag aus der Liste der PSTN-Verwendungseinträge aus, die für Ihre Bereitstellung definiert wurden, und wählen Sie einen Eintrag aus, um eine oder mehrere PstN-Verwendungen der Enterprise-VoIP zuzuordnen.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdatensätze finden Sie unter Anzeigen von PSTN-Verwendungsdatensätzen [in Skype for Business.](view-pstn-usage-records.md) > Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter "Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen [in Skype for Business".](voice-policy-and-pstn-usage-records.md) 
  
10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.
    
    > [!NOTE]
    > Im Gegensatz zu einer Voicerichtlinie, bei der die Reihenfolge, in der die PstN-Verwendungseinträge aufgeführt werden, wichtig ist, ist die Reihenfolge der PSTN-Verwendungsdatensätze in einer Sprachroute unerheblich. Es wird jedoch empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, z. B.: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
11. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
12. Klicken Sie auf **OK**.
    
13. Klicken Sie auf der Seite **Route** auf **Commit** und anschließend auf **Commit für alle**. 
    
    > [!NOTE]
    > Jedes Mal, wenn Sie eine Voiceroute erstellen oder ändern, müssen Sie den Befehl **"Commit** für alle" ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business](view-pstn-usage-records.md)
  
[Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md)

