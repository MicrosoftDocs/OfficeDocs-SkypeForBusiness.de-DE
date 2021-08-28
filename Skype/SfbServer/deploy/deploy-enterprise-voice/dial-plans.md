---
title: Erstellen oder Ändern eines Wählplans in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen Wählplan mithilfe der Skype for Business Server Systemsteuerung erstellen oder ändern.'
ms.openlocfilehash: e5e7f7cc0fc2edf0707025ed4b5e901c0a199021
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607632"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Erstellen oder Ändern eines Wählplans in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie einen Wählplan mithilfe der Skype for Business Server Systemsteuerung erstellen oder ändern.

### <a name="to-create-a-dial-plan"></a>So erstellen Sie einen Wählplan

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan**.

3. Klicken Sie auf der Seite **Wählplan** auf **Neu**, und wählen Sie einen Bereich für den Wählplan aus:

   - **Standortwählplan** werden auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einem Wählplan zugeordnet wurden. Wenn Sie **"Standort"** für den Bereich eines Wählplans auswählen, müssen Sie den Standort im Dialogfeld **"Standort auswählen"** auswählen. Wenn bereits ein Wählplan für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.

   - **Poolwählplan** kann auf ein PSTN-Gateway oder eine Registrierungsstelle angewendet werden. Wenn Sie **"Pool"** für den Bereich eines Wählplans auswählen, wählen Sie im Dialogfeld **"Dienst auswählen"** das PSTN-Gateway oder die Registrierungsstelle aus. Wenn bereits ein Wählplan für einen Dienst (PSTN-Gateway oder Registrierungsstelle) erstellt wurde, wird der Dienst nicht in der Liste angezeigt.

   - **Benutzerwählplan** kann auf bestimmte Benutzer oder Gruppen angewendet werden.

     > [!NOTE]
     > Nachdem Sie den Bereich für den Wählplan ausgewählt haben, kann dieser nicht mehr geändert werden.

4. Wenn Sie einen Wählplan erstellen, geben Sie im Dialogfeld **Neuer Wählplan** im Feld **Name** einen beschreibenden Namen ein. Nach dem Speichern kann dieser Name nicht mehr geändert werden.

    > [!NOTE]
    > Bei Standortwählplänen wird das **Feld "Name"** vorab mit dem Standortnamen aufgefüllt und kann nicht geändert werden.> Für Poolwählpläne wird das **Feld "Name"** mit dem Namen des PSTN-Gateways oder der Registrierungsstelle ausgefüllt und kann nicht geändert werden.

5. Das Feld **Einfacher Name** wird mit demselben Namen vorausgefüllt, der im Feld **Name** erscheint. Sie können dieses Feld optional bearbeiten, um einen aussagekräftigeren Namen anzugeben, der den Standort, Dienst oder Benutzer zur Anwendung des Wählplans besser beschreibt.

   > [!IMPORTANT]
   > Der **einfache Name** muss unter allen Wählplänen in Ihrer Bereitstellung eindeutig sein. 256 Unicode-Zeichen dürfen nicht überschritten werden. Jedes Zeichen kann ein alphabetisches oder numerisches Zeichen, ein Bindestrich (-), ein Punkt (.) oder ein Unterstrich (_).> **Nicht unterstützte** Zeichen umfassen Leerzeichen und reservierte Zeichen gemäß RFC 3966 ( <http://www.ietf.org/rfc/rfc3966.txt> ). Reservierte Zeichen, die im **einfachen Namen** **nicht unterstützt** werden, umfassen Folgendes:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

6. (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zum Wählplan ein.

7. (Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.

    > [!NOTE]
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.

8. (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können ein Präfix eingeben, das aus bis zu vier Zeichen besteht (#, * und 0-9).

    > [!NOTE]
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.

9. Führen Sie die folgenden Schritte aus, um Normalisierungsregeln für den Wählplan zuzuordnen und zu konfigurieren:

    - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Normalisierungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie dem Wählplan zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Erstellen oder Ändern einer Normalisierungsregel in Skype for Business](normalization-rules.md).

   - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Normalisierungsregel zu bearbeiten, die bereits den Wähleinstellungen zugeordnet ist.

   - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

   - Wenn Sie eine Normalisierungsregel aus den Wähleinstellungen entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

     > [!NOTE]
     > Jedem Satz mit Wähleinstellungen muss mindestens eine Normalisierungsregel zugeordnet sein. Informationen zum Ermitteln aller Normalisierungsregeln, die ein Wählplan erfordert, finden Sie unter [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in der Planungsdokumentation.

10. Stellen Sie sicher, dass die Normalisierungsregeln des Wählplans in der richtigen Reihenfolge angeordnet sind. Um die Position einer Regel in der Liste zu ändern, markieren Sie den Regelnamen, und klicken Sie dann auf den Nach-oben- oder Abwärtspfeil.

    > [!IMPORTANT]
    > Skype for Business Server durchläuft die Liste der Normalisierungsregel von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Satz mit Wähleinstellungen so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. > Die Standardregel **"Keep All** normalization rule^(\d {11} )$" stimmt mit einer beliebigen 11-stelligen Zahl überein. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die mit 11-stelligen Zahlen übereinstimmt, die mit 1425 beginnen, stellen Sie sicher, dass **Keep All** unter der restriktiveren ^(1425\d {7} )$-Regel sortiert ist.

11. (Optional) Geben Sie eine Nummer zum Testen der Wähleinstellungen ein, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

12. Klicken Sie auf **OK**.

13. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie einen Wählplan erstellen, müssen Sie den Befehl **Commit für alle Elemente ausführen** aufrufen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-modify-a-dial-plan"></a>So ändern Sie einen Satz mit Wähleinstellungen

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wähleinstellungen**.

4. Doppelklicken Sie auf der Seite **Wähleinstellungen** auf einen Satz mit Wähleinstellungen.

    > [!NOTE]
    > Bereich und Name der Wähleinstellungen wurden beim Erstellen der Wähleinstellungen festgelegt.  Sie können nicht geändert werden.

5. (Optional) Bearbeiten Sie im Abschnitt **Wähleinstellungen bearbeiten** das Feld **Einfacher Name** (dieses wird mit dem Namen im Feld **Name** vorausgefüllt), um einen beschreibenderen Namen einzugeben, der den Standort, Dienst oder Benutzer angibt, für den die Wähleinstellungen gelten.

    > [!IMPORTANT]
    > Der **einfache Name** muss unter allen Wählplänen innerhalb der Lync Server 2013-Bereitstellung eindeutig sein. Sie darf 256 Unicode-Zeichen nicht überschreiten, von denen jedes ein alphabetisches oder numerisches Zeichen, ein Bindestrich (-), ein Punkt (.), ein Pluszeichen (+) oder ein Unterstrich (_) sein kann. > Leerzeichen sind im Feld **"Einfacher Name"** nicht zulässig.

6. (Optional) Geben Sie im Feld **Beschreibung** beschreibende Informationen zu den Wähleinstellungen ein.

7. (Optional) Wenn Sie diese Wähleinstellungen als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Region für Einwahlkonferenzen** an. Wenn Sie diese Wähleinstellungen nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.

    > [!NOTE]
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Sätzen mit Wähleinstellungen zuzuordnen.

8. (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können ein Präfix eingeben, das aus bis zu vier Zeichen besteht (d. h. #, * und 0-9).

    > [!NOTE]
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.

9. Zuordnen und Konfigurieren von Normalisierungsregeln für die Wähleinstellungen:

   - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Normalisierungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie den Wähleinstellungen zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und den Wähleinstellungen zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Erstellen oder Ändern einer Normalisierungsregel in Skype for Business](normalization-rules.md).

   - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Normalisierungsregel zu bearbeiten, die bereits den Wähleinstellungen zugeordnet ist.

   - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

   - Wenn Sie eine Normalisierungsregel aus den Wähleinstellungen entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

     > [!NOTE]
     > Jedem Satz mit Wähleinstellungen muss mindestens eine Normalisierungsregel zugeordnet sein. Ausführliche Informationen zum Ermitteln aller Normalisierungsregeln, die ein Wählplan erfordert, finden Sie unter [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in der Planungsdokumentation.

10. Stellen Sie sicher, dass die Normalisierungsregeln des Wählplans in der richtigen Reihenfolge angeordnet sind. Um die Position einer Regel in der Liste zu ändern, markieren Sie den Regelnamen, und klicken Sie dann auf den Nach-oben- oder Abwärtspfeil.

    > [!IMPORTANT]
    > Skype for Business Server durchläuft die Liste der Normalisierungsregel von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Satz mit Wähleinstellungen so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. > Die Standardregel **"Keep All** normalization rule^(\d {11} )$" stimmt mit einer beliebigen 11-stelligen Zahl überein. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die mit 11-stelligen Zahlen übereinstimmt, die mit 1425 beginnen, stellen Sie sicher, dass **Keep All** unter der restriktiveren ^(1425\d {7} )$-Regel sortiert ist.

11. (Optional) Geben Sie eine Nummer zum Testen der Wähleinstellungen ein, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!NOTE]
    > Sie können einen Satz mit Wähleinstellungen speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter [Testen des VoIP-Routings](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

12. Klicken Sie auf **OK**.

13. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie einen Satz mit Wähleinstellungen erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)