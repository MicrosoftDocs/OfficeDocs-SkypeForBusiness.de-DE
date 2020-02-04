---
title: 'Lync Server 2013: Erstellen eines Wählplans'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d4647f374fd65c0be52da111b7ef2d41c0faae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a>Erstellen eines Wählplans in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-24_

Führen Sie die Schritte im folgenden Verfahren aus, um einen neuen Wählplan zu erstellen. Wenn Sie einen Wählplan bearbeiten möchten, lesen Sie [Ändern von Wählplänen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-create-a-dial-plan"></a>So erstellen Sie einen Wählplan

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan**.

4.  Klicken Sie auf der Seite **Wählplan** auf **Neu** und wählen Sie einen Bereich für den Wählplan aus:
    
      - **Standortwählplan** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einem Wählplan zugeordnet wurden. Wenn Sie die Einstellung **Standort** als Bereich für einen Wählplan auswählen, müssen Sie im Dialogfeld **Standort auswählen** den gewünschten Standort angeben. Wenn bereits ein Wählplan für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.
    
      - **Poolwählplan** kann auf ein PSTN-Gateway oder eine Registrierungsstelle angewendet werden. Wenn Sie die Einstellung **Pool** als Bereich für einen Wählplan auswählen, müssen Sie im Dialogfeld **Dienst auswählen** das gewünschte PSTN-Gateway oder die Registrierungsstelle angeben. Wenn bereits ein Wählplan für einen Dienst (PSTN-Gateway oder Registrierungsstelle) erstellt wurde, wird der Dienst nicht in der Liste angezeigt.
    
      - **Benutzerwählplan** kann auf bestimmte Benutzer oder Gruppen angewendet werden.
    
    <div>
    

    > [!NOTE]  
    > Nachdem Sie den Bereich für den Wählplan ausgewählt haben, kann dieser nicht mehr geändert werden.

    
    </div>

5.  Wenn Sie einen Wählplan erstellen, geben Sie im Dialogfeld **Neuer Wählplan** im Feld **Name** einen beschreibenden Namen ein. Nach dem Speichern kann dieser Name nicht mehr geändert werden.
    
    <div>
    

    > [!NOTE]  
    > Für Standortwählpläne wird das Feld <STRONG>Name</STRONG> mit dem Namen des Standorts vorausgefüllt und kann nicht geändert werden.<BR>Für Poolwählpläne wird das Feld <STRONG>Name</STRONG> mit dem Namen des PSTN-Gateways oder der Registrierungsstelle vorausgefüllt und kann nicht geändert werden.

    
    </div>

6.  Das Feld **Einfacher Name** wird mit demselben Namen vorausgefüllt, der im Feld **Name** erscheint. Sie können dieses Feld optional bearbeiten, um einen aussagekräftigeren Namen anzugeben, der den Standort, Dienst oder Benutzer zur Anwendung des Wählplans besser beschreibt.
    
    <div>
    

    > [!IMPORTANT]  
    > Der <STRONG>einfache Name</STRONG> muss bei allen Wählplänen innerhalb der lync Server-Bereitstellung eindeutig sein. Sie kann 256-Unicode-Zeichen nicht überschreiten, die jeweils ein alphabetisches oder numerisches Zeichen, einen Bindestrich (-), einen Punkt (.) oder einen Unterstrich (_) sein können.<BR>Zeichen, die <STRONG>nicht unterstützt werden</STRONG> , umfassen Leerzeichen und reservierte Zeichen gemäß der Definition in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt). Zu den <STRONG>nicht unterstützten</STRONG> Zeichen im Feld <STRONG>Einfacher Name</STRONG> gehören die folgenden:<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zum Wählplan ein.

8.  (Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.
    
    <div>
    

    > [!NOTE]  
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.

    
    </div>

9.  (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können einen Präfixwert mit bis zu vier Zeichen (\#, \*und 0-9) eingeben.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.

    
    </div>

10. Führen Sie die folgenden Schritte aus, um Normalisierungsregeln für den Wählplan zuzuordnen und zu konfigurieren:
    
      - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Normalisierungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie dem Wählplan zuordnen möchten und klicken Sie anschließend auf **OK**.
    
      - Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details einblenden**, um eine Normalisierungsregel zu bearbeiten, die bereits dem Wählplan zugeordnet ist. Ausführliche Informationen zum Bearbeiten der Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Details zum Bearbeiten der Kopie finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.
    
    <div>
    

    > [!NOTE]  
    > Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein. Informationen zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln in lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

11. Stellen Sie sicher, dass die Normalisierungsregeln für den Wählplan in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server durchsucht die Normalisierungsregel Liste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Wählplan so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.<BR>Die Standard <STRONG></STRONG> mäßige Normalisierungsregel <STRONG>^ (\d{11}) $</STRONG> entspricht einer beliebigen 11-stelligen Zahl. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die mit 11-stelligen Zahlen übereinstimmt, die mit 1425 beginnen, stellen Sie sicher, dass <STRONG>Alle beibehalten</STRONG> unter die restriktivere <STRONG>^ ({7}1425 \ d) $</STRONG> -Regel sortiert ist.

    
    </div>

12. (Optional) Geben Sie eine Nummer zum Testen des Wählplans ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Sie können einen Wählplan speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.

    
    </div>

13. Klicken Sie anschließend auf **OK**.

14. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie einen Wählplan erstellen, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> aufrufen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definieren von Normalisierungsregeln in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

