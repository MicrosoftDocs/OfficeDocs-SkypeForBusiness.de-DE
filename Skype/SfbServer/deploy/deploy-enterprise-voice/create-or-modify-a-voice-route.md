---
title: Erstellen oder Ändern einer VoIP-Route in Skype for Business
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine VoIP-Route in Skype for Business Server mithilfe der Skype for Business Server Systemsteuerung erstellen oder ändern.'
ms.openlocfilehash: a9ae7d0e1cff6f4fa49346b67c08253c108e026ec352606cf4f73fc0dc6a7640
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279343"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Erstellen oder Ändern einer VoIP-Route in Skype for Business
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine VoIP-Route in Skype for Business Server mithilfe der Skype for Business Server Systemsteuerung erstellen oder ändern.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>So erstellen Sie eine VoIP-Route mithilfe der Skype for Business Server Systemsteuerung

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf **Route**.
    
5. Klicken Sie auf **Neu**, um das Dialogfeld **Neue VoIP-Route** anzuzeigen.
    
6. Geben Sie unter **"Name"** einen beschreibenden Namen für die VoIP-Route ein.
    
7. (Optional) Geben Sie in **"Beschreibung"** zusätzliche beschreibende Informationen für die VoIP-Route ein.
    
8. Um die Muster anzugeben, die diese Route berücksichtigen soll, können Sie entweder das **Tool "Muster** erstellen" verwenden, um einen regulären Ausdruck zu generieren, oder den regulären Ausdruck manuell schreiben.
    
   - Geben Sie bei Verwendung des Tools **Muster für Vergleich erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise +425 ein, und klicken Sie dann auf **"Hinzufügen".** Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die Übereinstimmungsmuster ein, die diese Route  *nicht*  berücksichtigen soll. Wenn Sie z. B. Nummern, die mit +425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld **Ausnahmen** den Wert +425237 ein, und klicken Sie dann auf **OK.**
    
   - Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [".NET Framework Reguläre Ausdrücke".](/dotnet/standard/base-types/regular-expressions) 
    
9. Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine **alternative Anrufer-ID** angeben, die auf der Anzeige der Anrufer-ID des Empfängers angezeigt wird.
    
10. Wenn Sie der VoIP-Route einen oder mehrere Trunks zuordnen möchten, klicken Sie auf **"Hinzufügen",** und wählen Sie dann einen Trunk aus der Liste aus.
    
11. Wenn Sie der VoIP-Route eine oder mehrere PSTN-Verwendungen (Public Switched Telephone Network) zuordnen möchten, klicken Sie auf **"Auswählen",** und wählen Sie einen Datensatz aus der Liste der PSTN-Verwendungsdatensätze aus, die für Ihre Enterprise-VoIP Bereitstellung definiert wurden.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdatensätze finden Sie unter Anzeigen von [PSTN-Verwendungsdatensätzen in Skype for Business.](view-pstn-usage-records.md) > Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter [Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
12. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.
    
    > [!NOTE]
    > Im Gegensatz zu einer VoIP-Richtlinie, bei der die Reihenfolge, in der PSTN-Verwendungsdatensätze aufgeführt sind, wichtig ist, ist die Reihenfolge, in der PSTN-Verwendungsdatensätze in der VoIP-Route aufgeführt sind, nicht sehr wichtig. Es wird jedoch empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
13. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
14. Klicken Sie auf **OK**, um die VoIP-Route zu speichern.
    
    > [!IMPORTANT]
    > Jedes Mal, wenn Sie eine VoIP-Route erstellen, müssen Sie den Befehl **"Commit für alle"** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>So ändern Sie eine VoIP-Route

1. Öffnen Sie Skype for Business Server Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Route**.
    
3. Verwenden Sie auf der Seite **Route** eine der folgenden Methoden, um eine VoIP-Route zu ändern:
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
   - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten**, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Klicken Sie auf die neue Kopie der VoIP-Route, die Sie soeben erstellt haben, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
4. Geben Sie auf der Seite **VoIP-Route bearbeiten** im Feld **Name** einen beschreibenden Namen für die VoIP-Route ein.
    
5. (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.
    
6. Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Muster für Vergleich erstellen** verwenden, um einen regulären Ausdruck zu generieren, oder Sie erstellen manuell einen regulären Ausdruck.
    
   - Geben Sie bei Verwendung des Tools **Muster für Vergleich erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
    
   - **Anfangsziffern für Nummern, die Sie zulassen möchten**: Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise +425 ein, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
    
   - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die Übereinstimmungsmuster ein, die diese Route  *nicht*  berücksichtigen soll. Wenn Sie z. B. Nummern, die mit +425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld **Ausnahmen** den Wert +425237 ein, und klicken Sie dann auf **OK.**
    
   - Klicken Sie zum manuellen Definieren des Vergleichsmusters im **Tool "Muster zum Abgleichen** erstellen" auf **"Bearbeiten",** und geben Sie dann einen .NET Framework regulären Ausdruck ein, um das Vergleichsmuster für Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [".NET Framework Reguläre Ausdrücke".](/dotnet/standard/base-types/regular-expressions) 
    
7. Wählen Sie **"Anrufer-ID unterdrücken"** aus, wenn die ID des Telefons, das den ausgehenden Anruf durchführt, dem Anrufempfänger nicht angezeigt werden soll. Wenn Sie diese Option auswählen, müssen Sie eine **alternative Anrufer-ID** angeben, die auf der Anzeige der Anrufer-ID des Empfängers angezeigt wird.
    
8. Wenn Sie der VoIP-Route einen oder mehrere PSTN-Trunks (Public Switched Telephone Network) zuordnen möchten, klicken Sie auf **"Hinzufügen",** und wählen Sie dann einen Trunk aus der Liste aus.
    
9. Wenn Sie der VoIP-Route eine oder mehrere PSTN-Verwendungen zuordnen möchten, klicken Sie auf **"Auswählen",** und wählen Sie einen Datensatz aus der Liste der PSTN-Verwendungsdatensätze aus, die für Ihre Enterprise-VoIP Bereitstellung definiert wurden.
    
    > [!NOTE]
    > Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdatensätze finden Sie unter Anzeigen von [PSTN-Verwendungsdatensätzen in Skype for Business.](view-pstn-usage-records.md) > Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter [Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business.](voice-policy-and-pstn-usage-records.md) 
  
10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.
    
    > [!NOTE]
    > Im Gegensatz zu einer VoIP-Richtlinie, bei der die Reihenfolge, in der PSTN-Verwendungsdatensätze aufgeführt sind, wichtig ist, ist die Reihenfolge der PSTN-Verwendungsdatensätze in einer VoIP-Route unwichtig. Es wird jedoch empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, z. B.: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server durchläuft die Liste von oben nach unten.) 
  
11. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
12. Klicken Sie auf **OK**.
    
13. Klicken Sie auf der Seite **Route** auf **Commit** und anschließend auf **Commit für alle**. 
    
    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Route erstellen oder ändern, müssen Sie den Befehl **"Commit für alle"** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business](view-pstn-usage-records.md)
  
[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)