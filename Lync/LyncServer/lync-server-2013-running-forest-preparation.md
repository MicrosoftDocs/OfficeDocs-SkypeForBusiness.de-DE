---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
description: 'Lync Server 2013: Ausführung der Gesamtstrukturvorbereitung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577761"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a>Laufende Gesamtstrukturvorbereitung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Sie können Setup oder lync Server-Verwaltungsshell-Cmdlets zum Vorbereiten der Gesamtstruktur verwenden. Das Cmdlet, das die Gesamtstruktur vorbereitet, ist **Enable-CsAdForest**.

Nach der Vorbereitung der Gesamtstruktur, müssen Sie vor der Domänenvorbereitung sicherstellen, dass die globalen Einstellungen repliziert wurden.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>So verwenden Sie Setup zum Vorbereiten der Gesamtstruktur

1.  Melden Sie sich bei einem an eine Domäne angeschlossenen Computer als Mitglied der Gruppe "Organisations-Admins" für die Gesamtstruktur-Stammdomäne an.

2.  Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup.exe aus, um den Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.

4.  Klicken Sie in **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** auf **Ausführen**.

5.  Klicken Sie auf der Seite **Gesamtstruktur vorbereiten** auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Bei der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für lync Server 2013 platziert werden sollen. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.

    
    </div>

6.  Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.

7.  Erweitern Sie in der Spalte **Aktion** die Option **Gesamtstrukturvorbereitung**, suchen Sie nach einem **\<Success\>** Ausführungsergebnis am Ende jeder Aufgabe, um zu überprüfen, ob die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

8.  Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-In **Active Directory-Standorte und -Dienste** für den Domänencontroller der Gesamtstruktur-Stammdomäne aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation an den Standorten innerhalb von Minuten durchgeführt werden kann.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>So verwenden Sie Cmdlets zum Vorbereiten der Gesamtstruktur

1.  Melden Sie sich bei einem Domänencomputer als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur an.

2.  Installieren Sie lync Server Kernkomponenten wie folgt:
    
    1.  Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup.exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.
    
    3.  Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.
    
    4.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**. Das Installationsprogramm installiert die lync Server 2013 Kernkomponenten.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Ausführen
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Beispiel:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Wenn Sie den Parameter "GroupDomain" nicht angeben, wird standardmäßig die lokale Domäne verwendet. Wenn zuvor universelle Gruppen in einer Domäne erstellt wurden, bei der es sich nicht um die Standarddomäne handelt, muss der Parameter "GroupDomain" explizit angegeben werden.

5.  Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation für alle Domänencontroller, die im Snap-In **Active Directory-Standorte und -Dienste** für den Domänencontroller der Stammdomäne der Gesamtstruktur aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen.

6.  Überprüfen Sie, ob die Vorbereitung der Gesamtstruktur erfolgreich war. Führen Sie folgenden Befehl aus:
    
        Get-CsAdForest 
    
    Dieses Cmdlet gibt einen Wert von **LC \_ FORESTSETTINGS \_ Status \_ Ready** zurück, wenn die Gesamtstrukturvorbereitung erfolgreich war.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Vorbereiten der Gesamtstruktur auf lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

