---
title: 'Lync Server 2013: Technische Anforderungen für das Parken von Anrufen'
TOCTitle: Technische Anforderungen für das Parken von Anrufen
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204818(v=OCS.15)
ms:contentKeyID: 49293697
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Abschnitt werden die folgenden technischen Anforderungen für Parken von Anrufen beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Anforderungen für Audiodateien

## Hardwareanforderungen

Für die Anwendung zum Parken von Anrufen gelten die gleichen Hardwareanforderungen wie für den Front-End-Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

## Softwareanforderungen

Für die Anwendung zum Parken von Anrufen gelten die gleichen Anforderungen hinsichtlich Betriebssystem und erforderliche Komponenten wie für Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Alle Front-End-Server und Standard Edition-Server, auf denen die Anwendung zum Parken von Anrufen bereitgestellt ist, muss die Windows Media Format-Laufzeitkomponente für Server unter Windows Server 2008 R2 oder Microsoft Media Foundation für Server unter Windows Server 2012 oder Windows Server 2012 R2 installiert sein. Für Windows Server 2008 R2 wird die Windows Media Format-Laufzeitkomponente als Teil der Windows-Desktopdarstellung installiert. Die Windows Media Format-Laufzeitkomponente oder Microsoft Media Foundation ist für WMA-Dateien (Windows Media Audio) erforderlich, die in Parken von Anrufen als Wartemusik wiedergegeben werden.

## Portanforderungen

Die Anwendung zum Parken von Anrufen verwendet den folgenden Port:

  - **Port 5075**   Wird für SIP-Überwachungsanforderungen verwendet.


> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.



## Anforderungen für Audiodateien

Die Anwendung zum Parken von Anrufen unterstützt für Wartemusik lediglich WMA-Dateien (Windows Media Audio). Sie können Dateien für Wartemusik mit Microsoft Expression Encoder 4 anpassen. Expression Encoder 4 kann von der Webseite "Expression Encoder 4" unter der folgenden Adresse heruntergeladen werden: [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843). Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren. Das empfohlene Format für Wartemusikdateien für die Parken von Anrufen ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR oder 32 KBit/s.


> [!NOTE]
> Die konvertierte Datei wird über das Telefon nur mit 16&nbsp;kHz abgespielt, auch wenn diese mit 44&nbsp;kHz aufgezeichnet wurde.


