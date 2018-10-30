---
title: 'Lync Server 2013: Technische Anforderungen für die Ankündigungsanwendung'
TOCTitle: Technische Anforderungen für die Ankündigungsanwendung
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205413(v=OCS.15)
ms:contentKeyID: 49295994
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für die Ankündigungsanwendung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

In diesem Abschnitt werden die folgenden technischen Anforderungen für die Ansageanwendung beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Anforderungen für Audiodateien

## Hardwareanforderungen

Für die Ansageanwendung gelten die gleichen Hardwareanforderungen wie für den Front-End-Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

## Softwareanforderungen

Für die Ansageanwendung gelten die gleichen Anforderungen hinsichtlich Betriebssystem und erforderliche Komponenten wie für Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Auf allen Front-End-Server oder Standard Edition-Servern, auf denen die Ansageanwendung ausgeführt wird, muss die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 bzw. die Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein. Für Windows Server 2008 R2 wird die Windows Media Format-Laufzeitkomponente als Teil der Windows Desktop Experience installiert. Die Windows Media Format-Laufzeitkomponente oder Microsoft Media Foundation wird für WMA-Dateien (Windows Media Audio) benötigt, die die Ansageanwendung für Ansagen und Musik wiedergibt.

## Portanforderungen

Die Ansageanwendung verwendet den folgenden Port:

  - **Port 5071**   Wird für SIP-Überwachungsanforderungen verwendet


> [!NOTE]
> Dieser Port ist die Standardeinstellung, kann aber mit dem <STRONG>Set-CsApplicationServer</STRONG>-Cmdlet geändert werden. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.



## Anforderungen für Audiodateien

Die Ansageanwendung unterstützt das WAV-Dateiformat (Wave) und das WMA-Dateiformat (Windows Media Audio) für Musik und Ansagen. Die Anforderungen hinsichtlich Audiodateien für die Ansageanwendung sind die gleichen wie für die Reaktionsgruppenanwendung. Ausführliche Informationen finden Sie unter [Technische Anforderungen für Reaktionsgruppen in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

