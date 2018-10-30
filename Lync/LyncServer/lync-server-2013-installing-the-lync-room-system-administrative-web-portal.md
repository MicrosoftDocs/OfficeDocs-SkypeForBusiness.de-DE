---
title: Installieren des Webportals zur Verwaltung des Lync-Raumsystems
TOCTitle: Installieren des Webportals zur Verwaltung des Lync-Raumsystems
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn436326(v=OCS.15)
ms:contentKeyID: 59373616
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren des Webportals zur Verwaltung des Lync-Raumsystems

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie können das Webportal zur Verwaltung des Lync-Raumsystems aus dem Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044) herunterladen.

Wenn Sie das Webportal zur Verwaltung des Lync-Raumsystems installieren möchten, gehen Sie wie folgt vor.

1.  Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie folgendes Cmdlet in Lync Server-Verwaltungsshell ausführen:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Installieren Sie das Besprechungsraum-Administratorportal. Laden Sie dazu **LyncRoomAdminPortal.exe** herunter, und führen Sie das Programm als dann als Administrator aus.

3.  Öffnen Sie die Datei **Web.config** aus folgendem Speicherort:
    
    %Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler\\

4.  Ändern Sie in der Datei **Web.Config** den Wert von **PortalUserName** in den Benutzernamen, den Sie im Schritt 2 erstellt haben (Abschnitt "Konfigurieren der Voraussetzungen für das Webportal zur Verwaltung des Lync-Raumsystems", der für diesen Schritt empfohlene Name lautet **LRSApp**):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Da das Webportal zur Verwaltung des Lync-Raumsystems (LRS) eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort bei der Portalkonfiguration nicht angeben. Wenn für diesen Benutzer nicht die lokale Registrierungsstelle, sondern eine andere Registrierungsstelle verwendet wird, müssen Sie diese für den Benutzer angeben, indem Sie folgende Zeile in die Datei **Web.Config** einfügen:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Ist der verwendete Port nicht der Port 5061, fügen Sie folgende Zeile in die Datei **Web.Config** ein:
    
        <add key="PortalUserRegistrarPort" value="5061" />

## Überprüfen der Installation des Webportals zur Verwaltung des Lync-Raumsystems

Wenn Sie die Installation des Webportals zur Verwaltung des Lync-Raumsystems überprüfen möchten, gehen Sie wie folgt vor.


1.  Navigieren Sie auf einem Front-End-Server zur folgenden URL:
    
    https://\<fe-server\>/lrs
    
    Sie sollten keine Fehler sehen (siehe folgende Abbildung):
    
    ![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems")

2.  Wenn Sie keine Fehler sehen, versuchen Sie, über einen anderen Computer in der Topologie auf die folgende URL zuzugreifen:
    
    https://\<fe-server\>/lrs
    
    Damit Sie auf die Seite zugreifen können, müssen Sie die DNS-Einträge so hinzufügen, wie dies in "Required DNS Records for Automatic Client Sign-In" unter [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056) beschrieben ist.

