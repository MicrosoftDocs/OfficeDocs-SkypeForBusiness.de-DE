---
title: 'Lync Server 2013: Ausführen der Gesamtstrukturvorbereitung'
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
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Sie können mit den Setup-oder lync Server-Verwaltungsshell-Cmdlets die Gesamtstruktur vorbereiten. Das Cmdlet, das die Gesamtstruktur vorbereitet, ist **enable-CsAdForest**.

Nachdem Sie die Gesamtstruktur vorbereitet haben, müssen Sie überprüfen, ob die globalen Einstellungen repliziert wurden, bevor Sie die Domänenvorbereitung ausführen.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>So verwenden Sie Setup zum Vorbereiten der Gesamtstruktur

1.  Melden Sie sich bei einem Computer an, der einer Domäne als Mitglied der Gruppe "Organisations-Admins" für die Stammdomäne der Gesamtstruktur beigetreten ist.

2.  Führen Sie im lync Server 2013-Installationsordner oder-Medium Setup. exe aus, um den Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Active Directory vorbereiten** und warten Sie das Bestimmen des Bereitstellungsstatus ab.

4.  Klicken Sie in **Schritt 3: aktuelle Gesamtstruktur vorbereiten**auf **Ausführen**.

5.  Klicken Sie auf der Seite **Forest vorbereiten** auf **weiter**.
    
    <div>
    

    > [!NOTE]  
    > Mit der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für lync Server 2013 platziert werden sollen. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.

    
    </div>

6.  Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**.

7.  Erweitern Sie in der Spalte **Aktion** den Knoten **Gesamtstrukturvorbereitung**, suchen Sie am Ende jeder Aufgabe nach einem ** \<\> ** Ergebnis der erfolgreichen Ausführung, um zu überprüfen, ob die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

8.  Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-in **Active Directory-Standorte und-Dienste** für den Gesamtstruktur-Stammdomänencontroller aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation innerhalb der Websites innerhalb weniger Minuten erfolgen kann.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>So verwenden Sie Cmdlets zum Vorbereiten der Gesamtstruktur

1.  Melden Sie sich bei einem Computer an, der einer Domäne als Mitglied der Gruppe der Domänenadministratoren in der Stammdomäne der Gesamtstruktur beigetreten ist.

2.  Installieren Sie die lync Server Core-Komponenten wie folgt:
    
    1.  Führen Sie im lync Server 2013-Installationsordner oder-Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Wenn Sie aufgefordert werden, die Microsoft Visual C++-Installation zu installieren, klicken Sie auf **Ja**.
    
    3.  Im Dialogfeld "lync Server 2013-Setup" werden Sie aufgefordert, einen Speicherort zum Installieren der lync Server-Dateien anzuzeigen. Wählen Sie den Standardspeicherort aus, oder **Navigieren** Sie zu einem Speicherort Ihrer Wahl, und klicken Sie dann auf **Installieren**.
    
    4.  Aktivieren Sie auf der Seite Lizenzvertrag **die Kontrollkästchen Ich akzeptiere die Bedingungen des Lizenzvertrags**, und klicken Sie dann auf **OK**. Das Installationsprogramm installiert die lync Server 2013-Core-Komponenten.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Führen Sie folgenden Befehl aus:
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Beispiel:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Wenn Sie den GroupDomain-Parameter nicht angeben, ist der Standardwert die lokale Domäne. Wenn universelle Gruppen zuvor in einer Domäne erstellt wurden, die nicht die Standarddomäne ist, müssen Sie den GroupDomain-Parameter explizit angeben.

5.  Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-in **Active Directory-Standorte und-Dienste** für den Gesamtstruktur-Stammdomänencontroller aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen.

6.  Überprüfen Sie, ob die Gesamtstrukturvorbereitung erfolgreich war. Führen Sie folgenden Befehl aus:
    
        Get-CsAdForest 
    
    Dieses Cmdlet gibt den Wert des **LC\_-\_FORESTSETTINGS\_-Zustands bereit** zurück, wenn die Gesamtstrukturvorbereitung erfolgreich war.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

