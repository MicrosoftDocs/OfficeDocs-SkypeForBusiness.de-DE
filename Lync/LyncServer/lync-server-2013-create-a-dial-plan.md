---
title: 'Lync Server 2013: Erstellen von Wähleinstellungen'
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
ms.openlocfilehash: 382b04f9b0aa835d0230cb05fb56cb272546c038
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a>Erstellen von Wähleinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-24_

Führen Sie die folgenden Schritte aus, um einen Wählplan zu erstellen. Wenn Sie einen Wählplan bearbeiten möchten, finden Sie weitere Informationen unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-create-a-dial-plan"></a>So erstellen Sie einen Wählplan

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan**.

4.  Klicken Sie auf der Seite **Wählplan** auf **Neu**, und wählen Sie einen Bereich für den Wählplan aus:
    
      - **Standortwählplan** werden auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einem Wählplan zugeordnet wurden. Wenn Sie die Einstellung **Standort** als Bereich für einen Wählplan auswählen, müssen Sie im Dialogfeld **Standort auswählen** den gewünschten Standort angeben. Wenn bereits ein Wählplan für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.
    
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
    > Der <STRONG>einfache Name</STRONG> muss unter allen Wählplänen innerhalb der lync Server-Bereitstellung eindeutig sein. Er darf 256 Unicode-Zeichen nicht überschreiten, von denen jedes ein alphabetisches oder numerisches Zeichen, ein Bindestrich (-), ein Punkt (.) oder ein Unterstrich (_) sein kann.<BR><STRONG>Nicht unterstützte</STRONG> Zeichen umfassen Leerzeichen und reservierte Zeichen gemäßhttp://www.ietf.org/rfc/rfc3966.txt)der Definition in RFC 3966 (. Reservierte Zeichen, die im <STRONG>einfachen Namen</STRONG> <STRONG>nicht unterstützt</STRONG> werden, umfassen Folgendes:<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zum Wählplan ein.

8.  (Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.
    
    <div>
    

    > [!NOTE]  
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.

    
    </div>

9.  (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können einen Präfixwert von bis zu vier Zeichen eingeben (\#, \*und 0-9).
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.

    
    </div>

10. Führen Sie die folgenden Schritte aus, um Normalisierungsregeln für den Wählplan zuzuordnen und zu konfigurieren:
    
      - Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren Normalisierungsregeln auszuwählen. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie dem Wählplan zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Normalisierungsregel zu bearbeiten, die bereits den Wähleinstellungen zugeordnet ist. Ausführliche Informationen zum Bearbeiten der Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen zum Bearbeiten der Kopie finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Wenn Sie eine Normalisierungsregel aus den Wähleinstellungen entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.
    
    <div>
    

    > [!NOTE]  
    > Jedem Satz mit Wähleinstellungen muss mindestens eine Normalisierungsregel zugeordnet sein. Informationen zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial Plans and normalize Rules in lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

11. Stellen Sie sicher, dass die Normalisierungsregeln für die Wähleinstellungen in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server durchläuft die Liste Normalisierungsregel von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Satz mit Wähleinstellungen so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.<BR>Die standardmäßige Normalisierungsregel " <STRONG>Keep all</STRONG> " <STRONG>^ ({11}\d) $</STRONG> entspricht einer beliebigen 11-stelligen Zahl. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die 11-stelligen Zahlen entspricht, die mit 1425 beginnen, stellen Sie sicher, dass <STRONG>Alle beibehalten</STRONG> unter der restriktiveren <STRONG>^ (1425 \{7}d) $</STRONG> -Regel sortiert ist.

    
    </div>

12. (Optional) Geben Sie eine Nummer zum Testen der Wähleinstellungen ein, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Sie können einen Satz mit Wähleinstellungen speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.

    
    </div>

13. Klicken Sie auf **OK**.

14. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie einen Wählplan erstellen, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> aufrufen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

