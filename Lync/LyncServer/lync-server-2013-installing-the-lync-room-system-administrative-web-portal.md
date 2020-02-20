---
title: 'Lync Server 2013: Installieren des Administrator-Webportals für das lync Room-System'
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
ms.openlocfilehash: 24757a87279f64dd903ed4fdfb26169b606f899c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Installieren des Administrator-Webportals für das lync Room-System in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-04-09_

Sie können das Microsoft lync Room System administrative Webportal aus dem Microsoft Download Center herunterladen [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).

Führen Sie die folgenden Schritte aus, um das lync Room System-Verwaltungs Webportal zu installieren.

1.  Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in lync Server-Verwaltungsshell ausführen:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Um das Besprechungsraum Portal zu installieren, laden Sie **LyncRoomAdminPortal. exe** herunter, und führen Sie es dann als Administrator aus.

3.  Öffnen Sie die Datei "file. config" unter folgendem Speicherort:
    
    % Programmdateien%\\Microsoft lync Server 2013\\Webkomponenten\\-Besprechungsraum\\-\\Portal int-Handler\\

4.  Ändern Sie in der Datei "file. config" den PortalUserName in den in Schritt 2 erstellten Benutzernamen unter dem Abschnitt "Konfigurieren von Voraussetzungen für das lync Room System-Verwaltungs Portal" (der empfohlene Name im Schritt lautet LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Da das LRS-Verwaltungsportal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portal Konfiguration angeben. Wenn dieser Benutzer eine andere Registrierungsstelle als die lokale Registrierungsstelle verwendet, müssen Sie die Registrierungsstelle dafür angeben, indem Sie die folgende in der Datei "Internet. config" hinzufügen:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Wenn es sich bei dem verwendeten Port nicht um 5061 handelt, fügen Sie die folgende in der Datei "Internet. config" hinzu:
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Überprüfen der Installation des Administrator-Webportals von lync Room System

Gehen Sie folgendermaßen vor, um die Installation des lync Room System-Verwaltungsportals zu überprüfen:


1.  Navigieren Sie auf einem Front-End-Server zur folgenden URL:
    
    https://\<FE-Server\>/LRS
    
    Es sollten keine Fehler angezeigt werden, wie in der folgenden Abbildung dargestellt:
    
    ![Anmeldebildschirm des lync Room-System Administrator Portals](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm des lync Room-System Administrator Portals")

2.  Wenn keine Fehler angezeigt werden, versuchen Sie von einem anderen Computer in der Topologie aus auf die folgende URL zuzugreifen:
    
    https://\<FE-Server\>/LRS
    
    Um auf die Seite zugreifen zu können, müssen Sie die DNS-Einträge wie unter "erforderliche DNS-Einträge für die automatische Client Anmeldung" unter [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056)beschrieben hinzufügen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

