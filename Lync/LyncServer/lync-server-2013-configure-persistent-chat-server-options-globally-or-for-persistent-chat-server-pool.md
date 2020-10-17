---
title: 'Lync Server 2013: Konfigurieren von Optionen für den Server für beständigen Chat Global oder für den Serverpool für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520462"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Konfigurieren von Optionen für den Server für beständigen Chat Global oder für den Serverpool für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

In lync Server 2013 Systemsteuerung können Sie den Abschnitt **Konfiguration** für beständigen Chat auf der Seite **beständiger Chat** verwenden, um Einstellungen für beständigen Chat Global zu konfigurieren, auf denen Sie für alle Server Pools für beständigen Chat oder für einen bestimmten Serverpool für beständigen Chat gilt.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um die Unterstützung für beständigen Chat Server zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigen Chat Servern zur Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>So konfigurieren Sie Optionen für beständigen Chat Global

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.

4.  Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **neu,** und klicken Sie dann auf **Websitekonfiguration**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wählen Sie diese Option aus, wenn die Konfiguration auf alle in der Website bereitgestellten Server Pools für beständigen Chat angewendet werden soll. Klicken Sie auf <STRONG>Pool Konfiguration</STRONG> , wenn die Konfiguration auf einen bestimmten Server Pool für beständigen Chat angewendet werden soll.

    
    </div>

5.  Wählen Sie unter **Standort auswählen**den Standort aus, der für die Server Standortkonfiguration für beständigen Chat konfiguriert werden soll.

6.  Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.
    
      - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
        
        <div>
        

        > [!IMPORTANT]  
        > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Anzahl erweitern, werden weitere Nachrichten zwischengespeichert. Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie die Suche durchsuchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.

        
        </div>
    
      - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
        
        <div>
        

        > [!IMPORTANT]  
        > Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder frühere Gruppenchatclients, die Office Communications Server 2007 R2 &nbsp; Gruppenchatserver oder lync Server 2010 verwenden, Gruppenchat Dateien in einem Chatroom bereitstellen können. Der lync 2013-Client hat keine Dateiupload/Download-Funktion, wenn Sie also über eine reine lync 2013-Bereitstellung oder lync 2013-Client verfügen, ist es nicht möglich, Dateien in einem Chatroom für beständigen Chat Server bereitzustellen.

        
        </div>
    
      - Wählen Sie unter **Grenzwert für Teilnehmer Aktualisierung**den Grenzwert für Teilnehmer Aktualisierungen aus. Der Server für beständigen Chat sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Nummer erreicht. Standardmäßig lautet die Zahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der Server für beständigen Chat hinaus aufhört, die Dienstplan Aktualisierungen an verbundene Clients zu senden, die sich im Chatroom befinden.
    
      - (Optional) Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.
        
        Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den Server für beständigen Chat Server Software Development Kit (SDK) verwenden, ihn irgendwo hosten und die URL hier einfügen. Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Chatroom anzuzeigen oder zu erstellen, an die benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>So konfigurieren Sie Optionen für beständigen Chat für einen bestimmten Server Pool für beständigen Chat

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.

4.  Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.

5.  Wählen Sie unter **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat zugeordnet ist, der konfiguriert werden soll.

6.  Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.
    
      - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
        
        <div>
        

        > [!IMPORTANT]  
        > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Anzahl erweitern, werden weitere Nachrichten zwischengespeichert. Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie die Suche durchsuchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.

        
        </div>
    
      - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
        
        <div>
        

        > [!IMPORTANT]  
        > Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder frühere Gruppenchatclients (Office Communications Server 2007 R2 &nbsp; Gruppenchatserver oder lync Server 2010, Gruppenchat) Dateien in einem Chatroom bereitstellen können. Der lync 2013-Client hat keine Dateiupload/Download-Funktion, wenn Sie also über eine reine lync 2013-Bereitstellung oder lync 2013-Client verfügen, ist es nicht möglich, Dateien in einem Chatroom für beständigen Chat Server bereitzustellen.

        
        </div>
    
      - Wählen Sie unter **Grenzwert für Teilnehmer Aktualisierung**den Grenzwert für Teilnehmer Aktualisierungen aus. Der Server für beständigen Chat sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Nummer erreicht. Standardmäßig lautet die Zahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der Server für beständigen Chat hinaus aufhört, die Dienstplan Aktualisierungen an verbundene Clients zu senden, die sich im Chatroom befinden.
    
      - Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen.
        
        Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den Server für beständigen Chat Server Software Development Kit (SDK) verwenden, ihn irgendwo hosten und die URL hier einfügen. Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Chatroom anzuzeigen oder zu erstellen, an die benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

