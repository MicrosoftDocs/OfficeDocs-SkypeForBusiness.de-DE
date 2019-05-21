---
title: Erstellen oder Ändern eines Wählplans in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen Wählplan mithilfe der Skype for Business Server-Systemsteuerung erstellen oder ändern.'
ms.openlocfilehash: b2556a6b5a86b895f18db0daf981fd04ea49cda1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291651"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Erstellen oder Ändern eines Wählplans in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie einen Wählplan mithilfe der Skype for Business Server-Systemsteuerung erstellen oder ändern können.

### <a name="to-create-a-dial-plan"></a>So erstellen Sie einen Wählplan

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan**.

3. Klicken Sie auf der Seite **Wählplan** auf **Neu** und wählen Sie einen Bereich für den Wählplan aus:

   - **Standortwählplan** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einem Wählplan zugeordnet wurden. Wenn Sie **Website** für den Bereich eines Wählplans auswählen, müssen Sie die Website im Dialogfeld **Website auswählen** auswählen. Wenn bereits ein Wählplan für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.

   - **Poolwählplan** kann auf ein PSTN-Gateway oder eine Registrierungsstelle angewendet werden. Wenn Sie **Pool** für den Bereich eines Wählplans auswählen, wählen Sie im Dialogfeld **Dienst auswählen** das PSTN-Gateway oder die Registrierungsstelle aus. Wenn bereits ein Wählplan für einen Dienst (PSTN-Gateway oder Registrierungsstelle) erstellt wurde, wird der Dienst nicht in der Liste angezeigt.

   - **Benutzerwählplan** kann auf bestimmte Benutzer oder Gruppen angewendet werden.

     > [!NOTE]
     > Nachdem Sie den Bereich für den Wählplan ausgewählt haben, kann dieser nicht mehr geändert werden.

4. Wenn Sie einen Wählplan erstellen, geben Sie im Dialogfeld **Neuer Wählplan** im Feld **Name** einen beschreibenden Namen ein. Nach dem Speichern kann dieser Name nicht mehr geändert werden.

    > [!NOTE]
    > Bei Website Wählplänen ist das Feld **Name** mit dem Namen der Website gefüllt und kann nicht geändert werden. > für Pool-Wählpläne ist das Feld **Name** mit dem Namen des PSTN-Gateways oder der Registrierungsstelle belegt und kann nicht geändert werden.

5. Das Feld **Einfacher Name** wird mit demselben Namen vorausgefüllt, der im Feld **Name** erscheint. Sie können dieses Feld optional bearbeiten, um einen aussagekräftigeren Namen anzugeben, der den Standort, Dienst oder Benutzer zur Anwendung des Wählplans besser beschreibt.

   > [!IMPORTANT]
   > Der **einfache Name** muss bei allen Wählplänen in Ihrer Bereitstellung eindeutig sein. Sie kann 256-Unicode-Zeichen nicht überschreiten, die jeweils ein alphabetisches oder numerisches Zeichen, einen Bindestrich (-), einen Punkt (.) oder einen Unterstrich (_) aufweisen können. >-Zeichen, die **nicht unterstützt** werden,<http://www.ietf.org/rfc/rfc3966.txt>umfassen Leerzeichen und reservierte Zeichen, wie in RFC 3966 () definiert. Reservierte Zeichen, die im **einfachen Namen** **nicht unterstützt** werden, umfassen Folgendes: > ";" "/" "?" ":" "@"&amp;"" "=" "+" "$" ";"

6. (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zum Wählplan ein.

7. (Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.

    > [!NOTE]
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.

8. (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können ein Präfix eingeben, das aus bis zu vier Zeichen besteht (#, * und 0-9).

    > [!NOTE]
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.

9. Führen Sie die folgenden Schritte aus, um Normalisierungsregeln für den Wählplan zuzuordnen und zu konfigurieren:

    - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Normalisierungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie dem Wählplan zuordnen möchten und klicken Sie anschließend auf **OK**.

   - Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [erstellen oder Ändern einer Normalisierungsregel in Skype for Business](normalization-rules.md).

   - Klicken Sie auf den Regelnamen und anschließend auf **Details einblenden**, um eine Normalisierungsregel zu bearbeiten, die bereits dem Wählplan zugeordnet ist.

   - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

   - Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

     > [!NOTE]
     > Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein. Informationen zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter [Planen des ausgehenden VoIP-Routings in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in der Planungsdokumentation.

10. Überprüfen Sie, ob die Normalisierungsregeln des Wählplans in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie dann auf den nach oben oder nach unten weisenden Pfeil.

    > [!IMPORTANT]
    > Skype for Business Server durchsucht die Normalisierungsregel Liste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Wählplan so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. > die Standard **** mäßige Normalisierungsregel ^ (\d{11}) $ entspricht einer beliebigen 11-stelligen Zahl. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die mit 11-stelligen Zahlen übereinstimmt, die mit 1425 beginnen, stellen Sie sicher, dass **Alle beibehalten** unter die restriktivere ^ ({7}1425 \ d) $-Regel sortiert ist.

11. (Optional) Geben Sie eine Nummer zum Testen des Wählplans ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

12. Klicken Sie anschließend auf **OK**.

13. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie einen Wählplan erstellen, müssen Sie den Befehl **Commit für alle Elemente ausführen** aufrufen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-modify-a-dial-plan"></a>So ändern Sie einen Satz mit Wähleinstellungen

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan**.

4. Doppelklicken Sie auf der Seite **Wähleinstellungen** auf einen Satz mit Wähleinstellungen.

    > [!NOTE]
    > Bereich und Name der Wähleinstellungen wurden beim Erstellen der Wähleinstellungen festgelegt. Sie können nicht geändert werden.

5. (Optional) Bearbeiten Sie im Abschnitt **Wähleinstellungen bearbeiten** das Feld **Einfacher Name** (dieses wird mit dem Namen im Feld **Name** vorausgefüllt), um einen beschreibenderen Namen einzugeben, der den Standort, Dienst oder Benutzer angibt, für den die Wähleinstellungen gelten.

    > [!IMPORTANT]
    > Der **einfache Name** muss bei allen Wählplänen innerhalb der lync Server 2013-Bereitstellung eindeutig sein. Sie kann 256-Unicode-Zeichen nicht überschreiten, die jeweils ein alphabetisches oder numerisches Zeichen, einen Bindestrich (-), einen Punkt (.), ein Pluszeichen (+) oder einen Unterstrich (_) aufweisen können. > Leerzeichen sind im Feld " **einfacher Name** " nicht zulässig.

6. (Optional) Geben Sie im Feld **Beschreibung** beschreibende Informationen zu den Wähleinstellungen ein.

7. (Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.

    > [!NOTE]
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.

8. (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können ein Präfix eingeben, das aus bis zu vier Zeichen besteht (d. h. #, * und 0-9).

    > [!NOTE]
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.

9. Zuordnen und Konfigurieren von Normalisierungsregeln für die Wähleinstellungen:

   - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Normalisierungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie den Wähleinstellungen zuordnen möchten und klicken Sie anschließend auf **OK**.

   - Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [erstellen oder Ändern einer Normalisierungsregel in Skype for Business](normalization-rules.md).

   - Klicken Sie auf den Regelnamen und anschließend auf **Details einblenden**, um eine Normalisierungsregel zu bearbeiten, die bereits dem Wählplan zugeordnet ist.

   - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

   - Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

     > [!NOTE]
     > Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein. Details zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter [Planen des ausgehenden VoIP-Routings in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in der Planungsdokumentation.

10. Überprüfen Sie, ob die Normalisierungsregeln des Wählplans in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie dann auf den nach oben oder nach unten weisenden Pfeil.

    > [!IMPORTANT]
    > Skype for Business Server durchsucht die Normalisierungsregel Liste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Wählplan so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. > die Standard **** mäßige Normalisierungsregel ^ (\d{11}) $ entspricht einer beliebigen 11-stelligen Zahl. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die mit 11-stelligen Zahlen übereinstimmt, die mit 1425 beginnen, stellen Sie sicher, dass **Alle beibehalten** unter die restriktivere ^ (1425{7}\ d) $-Regel sortiert ist.

11. (Optional) Geben Sie eine Nummer zum Testen des Wählplans ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!NOTE]
    > Sie können einen Wählplan speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

12. Klicken Sie anschließend auf **OK**.

13. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie einen Wählplan erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)

