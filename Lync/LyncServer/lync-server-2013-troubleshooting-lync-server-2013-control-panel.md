---
title: 'Lync Server 2013: Problembehandlung bei der lync Server 2013-Systemsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff82a1e63a064d0053fc77614d6a9b5fa818c23e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Problembehandlung bei der lync Server 2013-Systemsteuerung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-07-28_

Dieses Thema enthält Informationen und Verfahren, die Ihnen bei der Problembehandlung beim Zugriff auf die lync Server 2013-Systemsteuerung helfen können.

<div>

## <a name="internet-browser-requirements"></a>Anforderungen des Internet Browsers

Die lync Server-Systemsteuerung setzt voraus, dass die Microsoft Silverlight-Browser-Plug-in-Version 4.0.50524.0 oder neueste Version installiert ist. Wenn Silverlight nicht installiert ist oder wenn eine frühere Version installiert ist, folgen Sie den Anweisungen in der Nachricht, um die erforderliche Version zu installieren.

<div>


> [!NOTE]  
> Andere Softwareanforderungen für lync Server Control Panel beziehen sich auf das Betriebssystem, auf dem lync Server Control Panel und alle anderen lync Server 2013-Verwaltungstools installiert werden können. Ausführliche Informationen finden Sie unter unter <A href="lync-server-2013-server-and-tools-operating-system-support.md">Stützung von Server-und Tools-Betriebssystemen in lync Server 2013</A> in der Dokumentation zur Unterstützung.



</div>

Wenn Ihr Internet Browser die Installation von Silverlight aufgrund von Sicherheitsüberlegungen blockiert, fügen Sie die URL (Uniform Resource Locator) hinzu, mit der die lync Server-Systemsteuerung der Liste der vertrauenswürdigen Websites geöffnet wird. Stellen Sie sicher, dass in den Sicherheitseinstellungen von Internet Explorer die Option **ActiveX-Steuerelemente und Plug-Ins ausführen** auf **aktiviert**festgesetzt ist. Ausführliche Informationen finden Sie [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)unter. Stellen Sie außerdem sicher, dass der Browser für die Verwendung von SSL 3,0 konfiguriert ist.

Wenn der Internet Browser für die Verwendung eines Proxyservers konfiguriert ist, überprüfen Sie, ob der Browser so konfiguriert ist, dass der Proxy Server für Websites umgangen wird, die automatisch als interne Websites erkannt werden. Oder fügen Sie die Adresse der Ausnahmeliste des Browsers in den Konfigurationseinstellungen des Proxyservers hinzu.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>DNS-Eintrag und Zertifikatanforderungen für die Administratorzugriffs-URL

Wenn Sie eine einfache URL für den Zugriff auf die lync Server-Systemsteuerung konfiguriert haben, stellen Sie sicher, dass Sie auch den statischen DNS-Host (Domain Name System)-Ressourceneintrag und das Zertifikat konfiguriert haben, das für die Verwendung dieser administrativen Zugriffs-URL erforderlich ist. Wenn Sie die Basis-URL jederzeit ändern, stellen Sie sicher, dass sich die Änderung im entsprechenden DNS-Eintrag und-Zertifikat widerspiegelt und dass Sie die *enable-CsComputer* auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren. Ausführliche Informationen finden Sie in den folgenden Themen in der Planungsdokumentation:

  - [Planung für einfache URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Eine schrittweise Anleitung zum Konfigurieren der Administratorzugriffs-URL finden Sie unter [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Anforderungen für Internet Informationsdienste (IIS)

Lync Server Control Panel ist eine der Komponenten von lync Server 2013, die Internet Informationsdienste (IIS) erfordert. Stellen Sie insbesondere sicher, dass die http-Umleitungs-und Windows-Authentifizierungsfeatures aktiviert sind und dass der World Wide Web Publishing Service (W3SVC) ausgeführt wird.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Weltweiter Publishing Service (Windows-Dienst)-Abhängigkeit

Wenn der www-Publishing Dienst beendet wird, können Sie nicht auf die lync Server-Systemsteuerung zugreifen. Sie können den Dienst mithilfe der Microsoft Management Console (MMC) für Windows-Dienste neu starten.

**So starten Sie den WWW-Publishing Dienst**

1.  Melden Sie sich bei dem Computer an, auf dem der www-Publishing Dienst als Teil der Internet Informationsdienste (IIS) installiert ist.

2.  Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.

3.  Klicken Sie mit der rechten Maustaste auf www- **Publishing Dienst**, und klicken Sie dann auf **Start**.

</div>

<div>

## <a name="application-pool-mode"></a>Anwendungs Pool Modus

Konfigurieren Sie IIS so, dass der CsManagementAppPool-Anwendungspool das Netzwerkdienstkonto als Prozessmodell Identität verwendet.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Benutzerrechte und-Berechtigungen

Sie müssen sich mit einem Domänenkonto, das ein Mitglied der CsAdministrator-Gruppe ist, oder mithilfe eines Kontos, an das Sie Benutzerrechte und-Berechtigungen delegiert haben, bei der lync Server Control Panel-Anwendung anmelden. Sie können sich nicht über ein lokales Computerkonto bei der lync Server Control Panel-Anwendung anmelden. Ausführliche Informationen zum Delegieren von administrativen Aufgaben über rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.

Wenn Sie eine einfache URL für den Zugriff auf die lync Server-Systemsteuerung verwenden, stellen Sie sicher, dass die Webservern den RTCUniversalServerAdmins-und RTCUniversalUserAdmins-Gruppen hinzugefügt werden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

