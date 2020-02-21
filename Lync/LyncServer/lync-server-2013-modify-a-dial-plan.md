---
title: 'Lync Server 2013: Ändern von Wähleinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2c4f922565b5b3af5613de4a5e43c79cf573410
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Ändern von Wähleinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, um einen vorhandenen Satz mit Wähleinstellungen zu ändern. Informationen zum Erstellen eines neuen Wählplans finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-modify-a-dial-plan"></a>So ändern Sie einen Satz mit Wähleinstellungen

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wähleinstellungen**.

4.  Doppelklicken Sie auf der Seite **Wähleinstellungen** auf einen Satz mit Wähleinstellungen.
    
    <div>
    

    > [!NOTE]  
    > Bereich und Name der Wähleinstellungen wurden beim Erstellen der Wähleinstellungen festgelegt.  Sie können nicht geändert werden.

    
    </div>

5.  (Optional) Bearbeiten Sie im Abschnitt **Wähleinstellungen bearbeiten** das Feld **Einfacher Name** (dieses wird mit dem Namen im Feld **Name** vorausgefüllt), um einen beschreibenderen Namen einzugeben, der den Standort, Dienst oder Benutzer angibt, für den die Wähleinstellungen gelten.
    
    <div>
    

    > [!IMPORTANT]  
    > Der <STRONG>einfache Name</STRONG> muss unter allen Wählplänen innerhalb der lync Server 2013-Bereitstellung eindeutig sein. Der Name darf nicht mehr als 256 Unicode-Zeichen umfassen und kann Buchstaben oder Zahlen, Bindestriche (-), Punkte (.), Pluszeichen (+) oder Unterstriche (_) enthalten.<BR>Leerzeichen sind im Feld <STRONG>Einfacher Name</STRONG> nicht zulässig.

    
    </div>

6.  (Optional) Geben Sie im Feld **Beschreibung** beschreibende Informationen zu den Wähleinstellungen ein.

7.  (Optional) Wenn Sie diese Wähleinstellungen als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Region für Einwahlkonferenzen** an. Wenn Sie diese Wähleinstellungen nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.
    
    <div>
    

    > [!NOTE]  
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Sätzen mit Wähleinstellungen zuzuordnen.

    
    </div>

8.  (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können einen Präfixwert von bis zu vier Zeichen eingeben (also \# \*,, und 0-9).
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.

    
    </div>

9.  Zuordnen und Konfigurieren von Normalisierungsregeln für die Wähleinstellungen:
    
      - Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren Normalisierungsregeln auszuwählen. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie den Wähleinstellungen zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und den Wähleinstellungen zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Normalisierungsregel zu bearbeiten, die bereits den Wähleinstellungen zugeordnet ist. Ausführliche Informationen zum Bearbeiten der Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen zum Bearbeiten der Kopie finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Wenn Sie eine Normalisierungsregel aus den Wähleinstellungen entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.
    
    <div>
    

    > [!NOTE]  
    > Jedem Satz mit Wähleinstellungen muss mindestens eine Normalisierungsregel zugeordnet sein. Ausführliche Informationen zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial Plans and normalize Rules in lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

10. Stellen Sie sicher, dass die Normalisierungsregeln für die Wähleinstellungen in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server durchläuft die Liste Normalisierungsregel von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Satz mit Wähleinstellungen so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.<BR>Die standardmäßige Normalisierungsregel " <STRONG>Keep all</STRONG> " <STRONG>^ ({11}\d) $</STRONG> entspricht einer beliebigen 11-stelligen Zahl. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die 11-stelligen Zahlen entspricht, die mit 1425 beginnen, stellen Sie sicher, dass <STRONG>Alle beibehalten</STRONG> unter der restriktiveren <STRONG>^ (1425 \ d{7}) $</STRONG> -Regel sortiert ist.

    
    </div>

11. (Optional) Geben Sie eine Nummer zum Testen der Wähleinstellungen ein, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Sie können einen Satz mit Wähleinstellungen speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.

    
    </div>

12. Klicken Sie auf **OK**.

13. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie einen Satz mit Wähleinstellungen erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

