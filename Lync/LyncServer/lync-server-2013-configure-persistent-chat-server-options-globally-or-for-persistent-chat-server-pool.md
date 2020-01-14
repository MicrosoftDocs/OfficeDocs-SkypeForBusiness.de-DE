---
title: 'Lync Server 2013: Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fedd0d1adb4149c3dc2ea41c5321259f571524f
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In der lync Server 2013-Systemsteuerung können Sie auf der Seite " **beständiger** Chat" den Abschnitt " **beständiger Chat** " verwenden, um die Einstellungen für beständigen Chat Global zu konfigurieren, wenn Sie für alle beständigen Chat Server Pools gelten, oder für einen bestimmten beständigen Chat Serverpool.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>So konfigurieren Sie beständige Chat Optionen Global

1.  Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.

4.  Klicken Sie auf der Seite **persistent Chat Configuration** auf **neu,** und klicken Sie dann auf **Websitekonfiguration**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wählen Sie diese Option aus, wenn die Konfiguration auf alle beständigen Chat Server Pools angewendet werden soll, die auf der Website bereitgestellt werden. Klicken Sie auf <STRONG>Poolkonfiguration</STRONG> , wenn die Konfiguration auf einen bestimmten beständigen Chat Server Pool angewendet werden soll.

    
    </div>

5.  Wählen Sie unter **Website auswählen**die Website aus, die für die Websitekonfiguration des beständigen Chat Servers konfiguriert werden soll.

6.  Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.
    
      - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
        
        <div>
        

        > [!IMPORTANT]  
        > Der beständige Chat Server speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Zahl erhöhen, werden weitere Nachrichten zwischengespeichert. Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie suchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.

        
        </div>
    
      - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
        
        <div>
        

        > [!IMPORTANT]  
        > Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder vorherige Gruppen-Chat-Clients, die Office Communications&nbsp;Server 2007 R2-Gruppen-Chat Server oder lync Server 2010 verwenden, Gruppen-Chat Dateien in einem Raum bereitstellen können. Wenn Sie über eine reine lync 2013-Bereitstellung oder einen lync 2013-Client verfügen, ist der lync 2013-Client nicht in der Lage, Dateien in einem beständigen Chat Server-Chatroom zu Posten.

        
        </div>
    
      - Wählen Sie in der **Teilnehmer Aktualisierungs Grenze**das Limit für Teilnehmer Updates aus. Der beständige Chat Server sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Nutzer diese Nummer erreicht hat. Standardmäßig ist die Nummer 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der beständige Chat Server keine Dienstplan Updates mehr an verbundene Clients sendet, die im Chatroom anwesend sind.
    
      - (Optional.) Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.
        
        Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den beständigen Chat Server Software Development Kit (SDK) verwenden, ihn an einer beliebigen Stelle hosten und die URL hier platzieren. Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Raum anzuzeigen oder zu erstellen, an Ihre benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>So konfigurieren Sie beständige Chat-Optionen für einen bestimmten beständigen Chat-Server Pool

1.  Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.

4.  Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.

5.  Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat zugeordnet ist und konfiguriert werden soll.

6.  Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.
    
      - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
        
        <div>
        

        > [!IMPORTANT]  
        > Der beständige Chat Server speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Zahl erhöhen, werden weitere Nachrichten zwischengespeichert. Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie suchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.

        
        </div>
    
      - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
        
        <div>
        

        > [!IMPORTANT]  
        > Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder vorherige Gruppen-Chat-Clients (Office Communications Server&nbsp;2007 R2-Gruppen-Chat Server oder lync Server 2010, Gruppen-Chat) Dateien in einem Raum bereitstellen können. Wenn Sie über eine reine lync 2013-Bereitstellung oder einen lync 2013-Client verfügen, ist der lync 2013-Client nicht in der Lage, Dateien in einem beständigen Chat Server-Chatroom zu Posten.

        
        </div>
    
      - Wählen Sie in der **Teilnehmer Aktualisierungs Grenze**das Limit für Teilnehmer Updates aus. Der beständige Chat Server sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Nutzer diese Nummer erreicht hat. Standardmäßig ist die Nummer 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der beständige Chat Server keine Dienstplan Updates mehr an verbundene Clients sendet, die im Chatroom anwesend sind.
    
      - Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen.
        
        Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den beständigen Chat Server Software Development Kit (SDK) verwenden, ihn an einer beliebigen Stelle hosten und die URL hier platzieren. Diese URL wird an den Client gesendet, damit ein Benutzer, der versucht, einen Raum anzuzeigen/zu erstellen, an Ihre benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

