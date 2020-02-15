---
title: 'Lync Server 2013: Ausführung der Schemavorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c58f50cb5c4668525450c4aa95b4a00513d5fc17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Durchführen Active Directory Schemavorbereitung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Sie können Setup oder lync Server-Verwaltungsshell-Cmdlets verwenden, um das Active Directory Schema vorzubereiten. Das Cmdlet für die Erweiterung des Active Directory-Schemas ist **Install-CsAdServerSchema**.

<div>


> [!NOTE]  
> Das Schema Vorbereitungs-Cmdlet (<STRONG>install-CsAdServerSchema</STRONG>) muss auf den Schemamaster zugreifen, der erfordert, dass der Remoteregistrierungsdienst aktiv ist und dass der Remote Registrierungsschlüssel aktiviert ist. Wenn der Remoteregistrierungsdienst auf dem Schemamaster nicht aktiviert werden kann, können Sie das Cmdlet lokal auf dem Schemamaster ausführen. Ausführliche Informationen zum Remotezugriff auf die Registrierung finden Sie im <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>Microsoft Knowledge Base-Artikel 314837, "Verwalten des Remotezugriffs auf die Registrierung" unter.



</div>

Stellen Sie nach Abschluss der Schemavorbereitung manuell sicher, dass die Schemapartition repliziert wurde, bevor Sie mit der Vorbereitung der Gesamtstruktur fortfahren. Ausführliche Informationen finden Sie unter [überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>So bereiten Sie das Schema der aktuellen Gesamtstruktur mithilfe von Setup vor

1.  Melden Sie sich bei einem Server in der Gesamtstruktur als Mitglied der Gruppe "Schema-Admins" und mit Administratorrechten auf dem Schemamaster an.

2.  Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup. exe aus, um den Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.

4.  Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.

5.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**.

6.  Das Installationsprogramm installiert die lync Server Kernkomponenten.

7.  Wenn der Bereitstellungs-Assistent bereit ist, klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.

8.  Klicken Sie unter **Schritt 1: Schema vorbereiten** auf **Ausführen**.

9.  Klicken Sie auf der Seite **Schema vorbereiten** auf **Weiter**.

10. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.

11. Erweitern Sie in der Spalte **Aktion** die Option **Schema prep**, suchen Sie nach dem ** \<\> ** Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Schema Vorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

12. Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.

13. Stellen Sie anhand des folgenden Verfahrens manuell sicher, dass die Schemaänderungen auf alle übrigen Domänencontroller repliziert wurden. Ausführliche Informationen finden Sie unter [überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>So bereiten Sie das Schema der aktuellen Gesamtstruktur mithilfe von Cmdlets vor

1.  Melden Sie sich bei einem Computer der Gesamtstruktur als Mitglied der Gruppe "Schema-Admins" und mit Administratorrechten für den Schemamaster an.

2.  Installieren Sie lync Server Kernkomponenten wie folgt:
    
    1.  Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.
    
    3.  Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.
    
    4.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**. Das Installationsprogramm installiert die lync Server 2013 Kernkomponenten.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Ausführen
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Wenn Sie den LDF-Parameter nicht angeben, ist der Standardwert der lync Server 2013 Installationspfad, der aus der Registrierung gelesen wird.
    
    Beispiel:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Überprüfen Sie mit dem folgenden Cmdlet, ob die Schemavorbereitung erfolgreich abgeschlossen wurde.
    
        Get-CsAdServerSchema 
    
    Dieses Cmdlet gibt den Wert des **Schema\_Versions\_Status\_Current** zurück, wenn die Schemavorbereitung erfolgreich war.

6.  Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.

7.  Stellen Sie anhand des folgenden Verfahrens manuell sicher, dass die Schemaänderungen auf alle übrigen Domänencontroller repliziert wurden. Ausführliche Informationen finden Sie unter [überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Vorbereiten des Active Directory Schemas in lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

