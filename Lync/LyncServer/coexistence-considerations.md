---
title: Überlegungen zur Koexistenz
TOCTitle: Überlegungen zur Koexistenz
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205131(v=OCS.15)
ms:contentKeyID: 49294898
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überlegungen zur Koexistenz

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Nach der Migration ist nur ein Lync Server 2013- Serverpool für beständigen Chat vorhanden und Sie können Ihre Bereitstellung der Vorgängerversion außer Betrieb setzen.

Vor dem Abschluss der Migration und bevor Sie Ihre aktuelle Gruppenchatserver-Bereitstellung vollständig außer Betrieb gesetzt haben, haben Sie gegebenenfalls einige der folgenden Bereitstellungen:

  - Lync Server 2013Serverpool für beständigen Chat, der in einem Lync Server 2013-Pool verwaltet werden muss.

  - Lync Server 2010-Gruppenchat-Pool, der in einem Lync Server 2010-Pool verwaltet werden muss.

  - Office Communications Server 2007 R2Gruppenchat-Pool, der in einem Office Communications Server 2007 R2-Pool verwaltet werden muss.

Diese Bereitstellungen können nebeneinander vorhanden sein. Die Kategorien, Chatrooms und Add-ins in einer Bereitstellung interagieren nicht mit denen einer anderen Bereitstellung.

Durch manuelle Konfiguration kann ein Legacyclient ( Gruppenchat-Client) für Office Communications Server 2007 R2Lync Server 2010-Gruppenchat oder Lync Server 2013 jeweils eine Verbindung zu einem Pool herstellen.

Der Lync 2013 (Client) kann nur mit dem Lync Server 2013- Serverpool für beständigen Chat interagieren, nicht mit den Legacypools von Gruppenchatserver. Um den Beständiger Chat in einem Lync 2013 (Client) verwenden zu können, muss der Benutzer im Lync 2013 verwaltet werden und durch eine Richtlinie berechtigt sein.

