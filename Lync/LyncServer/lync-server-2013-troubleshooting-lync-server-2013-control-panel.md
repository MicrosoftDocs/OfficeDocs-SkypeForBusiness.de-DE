---
title: 'Lync Server 2013: Problembehandlung bei lync Server 2013-Systemsteuerung'
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
ms.openlocfilehash: 07e670dc0871490e513023d3276ad80126be173b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Problembehandlung für die Lync Server 2013-Systemsteuerung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-07-28_

Dieses Thema enthält Informationen und Verfahren, die Sie bei der Problembehandlung für den Zugriff auf lync Server 2013 Systemsteuerung unterstützen können.

<div>

## <a name="internet-browser-requirements"></a>Internetbrowseranforderungen

Lync Server-Systemsteuerung erfordert, dass Microsoft Silverlight Browser-Plug-in-Version 4.0.50524.0 oder die neueste Version installiert ist. Wenn Silverlight nicht installiert ist oder wenn eine frühere Version installiert ist, befolgen Sie die Anweisungen in der Meldung, um die erforderliche Version zu installieren.

<div>


> [!NOTE]  
> Andere Softwareanforderungen für lync Server-Systemsteuerung beziehen sich auf das Betriebssystem, auf dem lync Server-Systemsteuerung und alle anderen lync Server 2013 Verwaltungstools installiert werden können. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-server-and-tools-operating-system-support.md">Betriebssystemunterstützung für Server und Tools in lync Server 2013</A> in der Unterstützungsdokumentation.



</div>

Wenn Ihr Internet Browser die Installation von Silverlight aufgrund von Sicherheitsüberlegungen blockiert, fügen Sie die URL (Uniform Resource Locator) hinzu, mit der lync Server-Systemsteuerung der Liste der vertrauenswürdigen Websites geöffnet wird. Stellen Sie sicher, dass in den Sicherheitseinstellungen von Internet Explorer die Option **ActiveX-Steuerelemente und Plugins ausführen****aktiviert** ist. Ausführliche Informationen finden Sie [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060)unter. Stellen Sie außerdem sicher, dass der Browser für die Verwendung von SSL 3.0 konfiguriert ist.

Wenn der Internetbrowser für die Verwendung eines Proxyservers konfiguriert ist, stellen Sie sicher, dass der Browser dafür konfiguriert ist, den Proxyserver für automatisch als intern erkannte  Websites zu umgehen. Alternativ können Sie auch in den Konfigurationseinstellungen für Proxyserver die Adresse der Ausnahmeliste des Browsers hinzufügen.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>DNS-Datensatz und Zertifikatanforderungen für die URL für den Verwaltungszugriff

Wenn Sie eine einfache URL für den Zugriff auf lync Server-Systemsteuerung konfiguriert haben, stellen Sie sicher, dass Sie auch den statischen Domain Name System (DNS) Hostressourceneintrag (a) und das für die Verwendung dieser administrativen Zugriffs-URL erforderliche Zertifikat konfiguriert haben. Wenn Sie die Basis-URL jederzeit ändern, stellen Sie sicher, dass die Änderung im entsprechenden DNS-Eintrag und-Zertifikat angezeigt wird und dass Sie das *enable-CsComputer* für jeden Director und Front-End-Server ausführen, um die Änderung zu registrieren. Ausführliche Informationen finden Sie in den folgenden Themen in der Planungsdokumentation:

  - [Planen von einfachen URLs in lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren der administrativen Zugriffs-URL finden Sie unter [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>IIS-Anforderungen (Internetinformationsdienste)

Lync Server-Systemsteuerung gehört zu den Komponenten von lync Server 2013, die Internet Information Services (IIS) erfordern. Stellen Sie vor allem sicher, dass die HTTP-Umleitung sowie die Windows-Authentifizierungsfunktionen aktiviert sind und der WWW-Publishingdienst (W3SVC) ausgeführt wird.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>WWW-Publishingdienst (Windows-Dienst) – Abhängigkeit

Wenn der WWW-Veröffentlichungsdienst angehalten ist, können Sie nicht auf lync Server-Systemsteuerung zugreifen. Starten Sie den Dienst mithilfe der Windows-MMC (Microsoft Management Console) "Dienste" neu.

**So starten Sie den WWW-Publishingdienst**

1.  Melden Sie sich bei dem Computer an, auf dem der WWW-Veröffentlichungsdienst als Teil von Internet Information Services (IIS) installiert ist.

2.  Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und **Dienste**.

3.  Klicken Sie mit der rechten Maustaste auf **WWW-Publishingdienst** und dann auf **Start**.

</div>

<div>

## <a name="application-pool-mode"></a>Modus des Anwendungspools

Konfigurieren Sie IIS so, dass der Anwendungspool "CsManagementAppPool" das Konto "Netzwerkdienst" als Prozessmodellidentität verwendet.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Benutzerrechte und -berechtigungen

Sie müssen sich bei lync Server-Systemsteuerung entweder mit einem Domänenkonto anmelden, das Mitglied der CsAdministrator-Gruppe ist, oder indem Sie ein Konto verwenden, an das Sie Benutzerrechte und-Berechtigungen delegiert haben. Sie können sich nicht mit einem lokalen Computerkonto bei lync Server-Systemsteuerung anmelden. Ausführliche Informationen zum Delegieren von Verwaltungsaufgaben über die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) finden Sie unter [Planning for Role-Based Access Control in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.

Wenn Sie eine einfache URL für den Zugriff auf lync Server-Systemsteuerung verwenden, stellen Sie sicher, dass den Gruppen RTCUniversalServerAdmins und RTCUniversalUserAdmins Webserver hinzugefügt werden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server 2013 Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

