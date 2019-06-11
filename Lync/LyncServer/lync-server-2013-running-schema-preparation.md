---
title: 'Lync Server 2013: Ausführen der Schemavorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Sie können das Active Directory-Schema mithilfe von Setup-oder lync Server-Verwaltungsshell-Cmdlets vorbereiten. Das Cmdlet, das das Active Directory-Schema erweitert, ist **install-CsAdServerSchema**.

<div>


> [!NOTE]  
> Das Schema Vorbereitungs-Cmdlet (<STRONG>install-CsAdServerSchema</STRONG>) muss auf den Schemamaster zugreifen, der erfordert, dass der Remoteregistrierungsdienst ausgeführt wird und dass der Remote Registrierungsschlüssel aktiviert ist. Wenn der Remoteregistrierungsdienst auf dem Schemamaster nicht aktiviert werden kann, können Sie das Cmdlet lokal auf dem Schemamaster ausführen. Details zum Remotezugriff auf die Registrierung finden Sie im <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>Microsoft Knowledge Base-Artikel 314837, "Verwalten des Remotezugriffs auf die Registrierung" unter.



</div>

Nachdem Sie die Schemavorbereitung abgeschlossen haben, überprüfen Sie manuell, ob die Schemapartition repliziert wurde, bevor Sie mit der Gesamtstrukturvorbereitung fortfahren. Ausführliche Informationen finden Sie unter [Überprüfen der Active Directory-Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>So verwenden Sie Setup zum Vorbereiten des Schemas der aktuellen Gesamtstruktur

1.  Melden Sie sich bei einem Server in Ihrer Gesamtstruktur als Mitglied der Gruppe Schemaadministratoren und mit Administratorrechten für den Schemamaster an.

2.  Führen Sie im lync Server 2013-Installationsordner oder-Medium Setup. exe aus, um den Bereitstellungs-Assistenten zu starten.

3.  Wenn Sie aufgefordert werden, die Microsoft Visual C++-Installation zu installieren, klicken Sie auf **Ja**.

4.  Im Dialogfeld "lync Server 2013-Setup" werden Sie aufgefordert, einen Speicherort zum Installieren der lync Server-Dateien anzuzeigen. Wählen Sie den Standardspeicherort aus, oder **Navigieren** Sie zu einem Speicherort Ihrer Wahl, und klicken Sie dann auf **Installieren**.

5.  Aktivieren Sie auf der Seite Lizenzvertrag **die Kontrollkästchen Ich akzeptiere die Bedingungen des Lizenzvertrags**, und klicken Sie dann auf **OK**.

6.  Das Installationsprogramm installiert die lync Server Core-Komponenten.

7.  Wenn der Bereitstellungs-Assistent bereit ist, klicken Sie auf **Active Directory vorbereiten**, und warten Sie, bis der Bereitstellungsstatus ermittelt wurde.

8.  Klicken Sie in **Schritt 1: Schema vorbereiten**auf **Ausführen**.

9.  Klicken Sie auf der Seite **Schema vorbereiten** auf **weiter**.

10. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**.

11. Erweitern Sie in der Spalte **Aktion** die **Schema**Vorbereitung, suchen Sie ** \<nach\> ** dem Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Schemavorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

12. Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.

13. Überprüfen Sie manuell, ob die Schemaänderungen auf alle anderen Domänencontroller repliziert wurden. Ausführliche Informationen finden Sie unter [Überprüfen der Active Directory-Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>So verwenden Sie Cmdlets zum Vorbereiten des Schemas der aktuellen Gesamtstruktur

1.  Melden Sie sich bei einem Computer in der Gesamtstruktur als Mitglied der Gruppe Schemaadministratoren und mit Administratorrechten für den Schemamaster an.

2.  Installieren Sie die lync Server Core-Komponenten wie folgt:
    
    1.  Führen Sie im lync Server 2013-Installationsordner oder-Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Wenn Sie aufgefordert werden, die Microsoft Visual C++-Installation zu installieren, klicken Sie auf **Ja**.
    
    3.  Im Dialogfeld "lync Server 2013-Setup" werden Sie aufgefordert, einen Speicherort zum Installieren der lync Server-Dateien anzuzeigen. Wählen Sie den Standardspeicherort aus, oder **Navigieren** Sie zu einem Speicherort Ihrer Wahl, und klicken Sie dann auf **Installieren**.
    
    4.  Aktivieren Sie auf der Seite Lizenzvertrag **die Kontrollkästchen Ich akzeptiere die Bedingungen des Lizenzvertrags**, und klicken Sie dann auf **OK**. Das Installationsprogramm installiert die lync Server 2013-Core-Komponenten.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Führen Sie folgenden Befehl aus:
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Wenn Sie den LDF-Parameter nicht angeben, ist der Standardwert der lync Server 2013-Installationspfad, der aus der Registrierung gelesen wird.
    
    Beispiel:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Verwenden Sie das folgende Cmdlet, um zu überprüfen, ob die Schemavorbereitung bis zum Abschluss ausgeführt wurde.
    
        Get-CsAdServerSchema 
    
    Dieses Cmdlet gibt den Wert des **Schema\_Versions\_Status\_Current** zurück, wenn die Schemavorbereitung erfolgreich war.

6.  Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.

7.  Überprüfen Sie manuell, ob die Schemaänderungen auf alle anderen Domänencontroller repliziert wurden. Ausführliche Informationen finden Sie unter [Überprüfen der Active Directory-Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Überprüfen der Active Directory-Schemareplikation in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

