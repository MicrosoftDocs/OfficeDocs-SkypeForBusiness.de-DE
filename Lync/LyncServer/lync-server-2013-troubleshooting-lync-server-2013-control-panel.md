---
title: Problembehandlung für die Lync Server 2013-Systemsteuerung
TOCTitle: Problembehandlung für die Lync Server 2013-Systemsteuerung
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg195689(v=OCS.15)
ms:contentKeyID: 49294033
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Problembehandlung für die Lync Server 2013-Systemsteuerung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Dieses Thema enthält Informationen und Vorgehensweisen, die die Fehlerbehandlung beim Zugriff auf die Systemsteuerung für Lync Server 2013 erleichtern.

## Internetbrowseranforderungen

Lync Server-Systemsteuerung erfordert die Installation von Microsoft Silverlight-Browser-Plug-In Version 4.0.50524.0 oder höher. Wenn Silverlight nicht installiert ist, oder eine niedrigere Version installiert ist, folgen Sie den Anweisungen in der Meldung, um die benötigte Version zu installieren.


> [!NOTE]
> Andere Softwareanforderungen für Lync Server-Systemsteuerung hängen vom Betriebssystem ab, unter dem Lync Server-Systemsteuerung und alle anderen Lync Server 2013-Verwaltungstools installiert werden können. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-server-and-tools-operating-system-support.md">Betriebssystemunterstützung für Server und Tools in Lync Server 2013</A> in der Unterstützungsdokumentation.



Wenn der Internetbrowser die Installation von Silverlight aus Sicherheitsgründen blockiert, fügen Sie die URL (Uniform Resource Locator) zum Öffnen der Lync Server-Systemsteuerung der Liste mit vertrauenswürdigen Websites hinzu. Stellen Sie sicher, dass in den Sicherheitseinstellungen von Internet Explorer die Option **ActiveX-Steuerelemente und Plug-Ins ausführenaktiviert** ist. Ausführliche Informationen finden Sie unter [http://go.microsoft.com/fwlink/?linkid=214060\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=214060%26clcid=0x407). Stellen Sie außerdem sicher, dass der Browser für die Verwendung von SSL 3.0 konfiguriert ist.

Wenn der Internetbrowser für die Verwendung eines Proxyservers konfiguriert ist, stellen Sie sicher, dass der Browser dafür konfiguriert ist, den Proxyserver für automatisch als intern erkannte Websites zu umgehen. Alternativ können Sie auch in den Konfigurationseinstellungen für Proxyserver die Adresse der Ausnahmeliste des Browsers hinzufügen.

## DNS-Datensatz und Zertifikatanforderungen für die URL für den Verwaltungszugriff

Wenn Sie eine einfache URL für den Zugriff auf die Lync Server-Systemsteuerung konfiguriert haben, stellen Sie sicher, dass Sie auch den Ressourceneintrag für den statischen DNS-Host (Domain Name System) (A) und das Zertifikat konfiguriert haben, die für die Verwendung dieser URL für den Verwaltungszugriff erforderlich sind. Wenn Sie die Basis-URL ändern, stellen Sie sicher, dass die Änderung im entsprechenden DNS-Datensatz und Zertifikat übernommen wird, und dass Sie *Enable-CsComputer* auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren. Ausführliche Informationen finden Sie in den folgenden Themen in der Planungsdokumentation:

  - [Planung für einfache URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Schrittanleitungen für die Konfiguration der URL für den Verwaltungszugriff finden Sie unter [Bearbeiten oder Konfigurieren einfacher URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.


> [!NOTE]
> Ist auf Ihrem Webserver mehr als ein Netzwerkadapter vorhanden, müssen Sie für jeden zusätzlichen Netzwerkadapter manuelle DNS-Konfigurationen vornehmen, damit DNS-Auflösung ordnungsgemäß funktioniert.



## IIS-Anforderungen (Internetinformationsdienste)

Lync Server-Systemsteuerung ist eine der Komponenten von Lync Server 2013, die Internetinformationsdienste (Internet Information Services, IIS) erfordern. Stellen Sie vor allem sicher, dass die HTTP-Umleitung sowie die Windows-Authentifizierungsfunktionen aktiviert sind und der WWW-Publishingdienst (W3SVC) ausgeführt wird.

## WWW-Publishingdienst (Windows-Dienst) – Abhängigkeit

Wenn der WWW-Publishingdienst angehalten wird, können Sie nicht auf Lync Server-Systemsteuerung zugreifen. Starten Sie den Dienst mithilfe der Windows-MMC (Microsoft Management Console) "Dienste" neu.

**So starten Sie den WWW-Publishingdienst**

1.  Melden Sie sich am Computer an, auf dem der WWW-Publishingdienst als Teil der Internetinformationsdienste (Internet Information Services, IIS) installiert ist.

2.  Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und **Dienste**.

3.  Klicken Sie mit der rechten Maustaste auf **WWW-Publishingdienst** und dann auf **Start**.

## Modus des Anwendungspools

Konfigurieren Sie IIS so, dass der Anwendungspool "CsManagementAppPool" das Konto "Netzwerkdienst" als Prozessmodellidentität verwendet.

## Benutzerrechte und -berechtigungen

Verwenden Sie für die Anmeldung an Lync Server-Systemsteuerung entweder ein Domänenkonto, das Mitglied der Gruppe "CsAdministrator" ist, oder ein Konto, an das Sie Benutzerrechte und -berechtigungen delegiert haben. Sie können sich nicht mit einem lokalen Computerkonto an Lync Server-Systemsteuerung anmelden. Ausführliche Informationen zum Delegieren von Verwaltungsaufgaben mit der rollenbasierten Zugriffssteuerung (RBAC) finden Sie unter [Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.

Wenn Sie eine einfache URL für den Zugriff auf Lync Server-Systemsteuerung verwenden, stellen Sie sicher, dass den Gruppen "RTCUniversalServerAdmins" und "RTCUniversalUserAdmins" Webserver hinzugefügt sind.

## Siehe auch

#### Konzepte

[Lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)

