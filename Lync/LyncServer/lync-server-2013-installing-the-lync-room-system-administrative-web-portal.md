---
title: 'Lync Server 2013: Installieren des lync Room System administrative Web Portals'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcfc78429ef021afcb0ed286ad86a39e63bfbf62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Installing the Lync Room System Administrative Web Portal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-04-09_

Sie können das administrative Webportal für Microsoft lync Room System aus dem Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)herunterladen.

Führen Sie die folgenden Schritte aus, um das lync Room System administrative Web Portal zu installieren.

1.  Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in der lync Server-Verwaltungsshell ausführen:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Zum Installieren des Besprechungsraum Portals laden Sie **LyncRoomAdminPortal. exe** herunter, und führen Sie es dann als Administrator aus.

3.  Öffnen Sie die Datei Web.config aus folgendem Speicherort:
    
    % Program Files%\\Microsoft lync Server 2013\\Webkomponenten\\Besprechungsraum-\\Portal\\int-Handler\\

4.  Ändern Sie in der Datei Web. config die PortalUserName in den in Schritt 2 erstellten Benutzernamen im Abschnitt "Konfigurieren von Voraussetzungen für das lync Room System Admin Portal" (der empfohlene Name im Schritt lautet LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Da das LRS-Administrator Portal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portalkonfiguration angeben. Wenn für diesen Benutzer nicht die lokale Registrierungsstelle, sondern eine andere Registrierungsstelle verwendet wird, müssen Sie diese für den Benutzer angeben, indem Sie folgende Zeile in die Datei Web.Config einfügen:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Wenn der verwendete Port nicht der Port 5061 ist, fügen Sie folgende Zeile in die Datei Web.Config ein: 
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Überprüfen der Installation des lync Room System administrative Web Portals

Gehen Sie wie folgt vor, um die Installation des lync Room System administrative Web Portals zu überprüfen:


1.  Navigieren Sie auf einem Front-End-Server zur folgenden URL:
    
    https://\<FE-Server\>/LRS
    
    Sie sollten keine Fehler sehen (siehe folgende Abbildung):
    
    ![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems")

2.  Wenn Sie keine Fehler sehen, versuchen Sie, über einen anderen Computer in der Topologie auf die folgende URL zuzugreifen:
    
    https://\<FE-Server\>/LRS
    
    Wenn Sie auf die Seite zugreifen möchten, müssen Sie die DNS-Einträge hinzufügen, wie unter "erforderliche DNS-Einträge für die automatische Client [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)Anmeldung" beschrieben ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

