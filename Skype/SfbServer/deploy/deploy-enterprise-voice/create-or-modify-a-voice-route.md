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
ms.openlocfilehash: c6f1e50971551866cfa6cb12eb6a259ac2f932f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105841"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Erstellen oder Ändern einer Sprachroute in Skype for Business
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine Sprachroute in Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung erstellen oder ändern.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>So erstellen Sie eine Sprachroute mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf **Route**.
    
5. Klicken Sie auf **Neu**, um das Dialogfeld **Neue VoIP-Route** anzuzeigen.
    
6. Geben **Sie unter Name** einen beschreibenden Namen für die Sprachroute ein.
    
7. (Optional) Geben **Sie unter Beschreibung** zusätzliche beschreibende Informationen für die Voiceroute ein.
    
8. Um die Muster anzugeben, für die diese Route  verwendet werden soll, können Sie entweder das Tool Erstellen eines Musters zum Anpassen verwenden, um einen regulären Ausdruck zu generieren, oder den regulären Ausdruck manuell schreiben.
    
   - Geben Sie bei Verwendung des Tools **Muster für Vergleich erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise +425 ein, und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein,  *für*  die diese Route nicht verwendet werden soll. Um z. B. Nummern, die mit +425237 beginnen, von der Route auszuschließen, geben Sie im Feld Ausnahmen den Wert +425237 ein, und klicken Sie dann auf **OK**. 
    
   - Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Weitere Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [".NET Framework Reguläre Ausdrücke"](/dotnet/standard/base-types/regular-expressions). 
    
9. Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine alternative **Anrufer-ID angeben,** die auf der Anzeige der Anrufer-ID des Empfängers angezeigt wird.
    
10. Klicken Sie auf Hinzufügen, und wählen  Sie dann einen Trunk aus der Liste aus, um der Sprachroute einen oder mehrere Trunks zuzuordnen.
    
11. Klicken Sie auf Auswählen, und wählen Sie einen Datensatz aus der  Liste der PSTN-Verwendungsdatensätze aus, die für Ihre Bereitstellung definiert wurden, um der Voiceroute eine oder mehrere Public Switched Telephone Network (PST Enterprise-VoIP N)-Verwendungen zuzuordnen.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdatensätze finden Sie unter [View PSTN usage records in Skype for Business](view-pstn-usage-records.md). > Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von [PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
12. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.
    
    > [!NOTE]
    > Im Gegensatz zu einer Voicerichtlinie, bei der die Reihenfolge, in der PSTN-Verwendungsdatensätze aufgeführt werden, wichtig ist, ist die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Voiceroute aufgeführt werden, unerheblich. Es wird jedoch empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
13. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
14. Klicken Sie auf **OK**, um die VoIP-Route zu speichern.
    
    > [!IMPORTANT]
    > Wenn Sie eine Voiceroute erstellen, müssen Sie den **Befehl Commit Alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen finden Sie [unter Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md). 
  
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
    
   - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein,  *für*  die diese Route nicht verwendet werden soll. Um z. B. Nummern, die mit +425237 beginnen, von der Route auszuschließen, geben Sie im Feld Ausnahmen den Wert +425237 ein, und klicken Sie dann auf **OK**. 
    
   - Klicken Sie zum manuellen  Definieren  des Übereinstimmungsmusters im Tool Muster zum Abgleich erstellen auf Bearbeiten, und geben Sie dann einen regulären .NET Framework-Ausdruck ein, um das übereinstimmende Muster für Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Weitere Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [".NET Framework Reguläre Ausdrücke"](/dotnet/standard/base-types/regular-expressions). 
    
7. Wählen **Sie Anrufer-ID** unterdrücken aus, wenn die ID des Telefons, das den ausgehenden Anruf an den Anrufempfänger weiterruft, nicht angezeigt werden soll. Wenn Sie diese Option auswählen, müssen Sie eine alternative **Anrufer-ID angeben,** die auf der Anzeige der Anrufer-ID des Empfängers angezeigt wird.
    
8. Klicken Sie auf **Hinzufügen,** und wählen Sie dann einen Trunk aus der Liste aus, um einen oder mehrere PstN-Trunks (Public Switched Telephone Network, PSTN) der Voiceroute zuzuordnen.
    
9. Klicken Sie zum Zuordnen einer oder mehreren  PSTN-Verwendungen zur Voiceroute auf Auswählen, und wählen Sie einen Datensatz aus der Liste der PSTN-Verwendungsdatensätze aus, die für Ihre bereitstellung Enterprise-VoIP wurden.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdatensätze finden Sie unter [View PSTN usage records in Skype for Business](view-pstn-usage-records.md). > Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md). 
  
10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.
    
    > [!NOTE]
    > Im Gegensatz zu einer Sprachrichtlinie, bei der die Reihenfolge, in der PSTN-Verwendungsdatensätze aufgeführt werden, wichtig ist, ist die Reihenfolge der PSTN-Verwendungsdatensätze in einer Sprachroute unerheblich. Es wird jedoch empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, z. B.: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
11. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
12. Klicken Sie auf **OK**.
    
13. Klicken Sie auf der Seite **Route** auf **Commit** und anschließend auf **Commit für alle**. 
    
    > [!NOTE]
    > Wenn Sie eine Voiceroute erstellen oder ändern, müssen Sie den **Befehl Commit für** alle ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie [unter Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business](view-pstn-usage-records.md)
  
[Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md)