---
title: 'Lync Server 2013: Bereitstellen des Servers für beständigen Chat'
TOCTitle: Bereitstellen des Servers für beständigen Chat
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205357(v=OCS.15)
ms:contentKeyID: 49295693
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen des Servers für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-03-31_

Lync Server 2013, Server für beständigen Chat ist Bestandteil der Lync Server 2013-Infrastruktur.

Sie müssen die folgenden Schritte ausführen, um den Server für beständigen Chat bereitzustellen:

  - Verwenden Sie den Topologie-Generator, um die Topologie zu definieren oder zu importieren, und veröffentlichen Sie anschließend die Topologie und die Komponenten, die Sie bereitstellen möchten.

  - Bereiten Sie Ihre Umgebung für die Bereitstellung von Server für beständigen Chat-Komponenten vor.

  - Installieren und konfigurieren Sie Server für beständigen Chat-Komponenten für Ihre Bereitstellung.

Server für beständigen Chat ist mit Lync Server 2013Enterprise Edition als separater Pool erhältlich (nicht in Koexistenz mit den Enterprise Edition- Front-End-Servern). Server für beständigen Chat benötigt einen SQL Server- Back-End-Server im Enterprise Edition-Pool zum Speichern der Chatroominhalte und sonstiger relevanter Metadaten. Es wird empfohlen, den **PersistentChatStore** auf einem dedizierten SQL Server- Back-End-Server zu installieren, auch wenn die Koexistenz von Lync Server 2013- Back-End-Server und **PersistentChatStore** in derselben SQL Server-Instanz unterstützt wird.

Server für beständigen Chat kann auch mit Lync Server 2013Standard Edition bereitgestellt werden. In diesem Fall befindet sich der **PersistentChatService**- Front-End-Server auf dem Standard Edition-Computer, und der **PersistentChatStore**- Back-End-Server kann in der lokalen SQL Server Express-Instanz bereitgestellt werden.

Ausführliche Informationen zu den unterstützten Zusammenstellungskonfigurationen finden Sie unter [Unterstützte Serverzusammenstellungen in Lync Server 2013](lync-server-2013-supported-server-collocation.md).


> [!IMPORTANT]
> Die hohe Verfügbarkeit wird für Server für beständigen ChatStandard Edition nicht unterstützt. Leistung und Skalierung sind beeinträchtigt. Darüber hinaus werden nur neue Server für beständigen Chat- Standard Edition-Server unterstützt. Das Upgrade von Lync Server 2010, Gruppenchatserver auf einen Lync Server 2013Server für beständigen ChatStandard Edition wird nicht unterstützt.



Falls in Ihrer Organisation Konformitätsunterstützung erforderlich ist, können Sie den Server für beständigen Chat-Konformitätsdienst auf dem Server für beständigen Chat- Front-End-Server installieren. Eine separate Datenbank ist für die Konformität erforderlich.

Für jede Topologie ist mindestens ein Server mit installiertem Lync Server 2013 und ein Server mit installierter SQL Server-Datenbanksoftware erforderlich.

Verwenden Sie den Topologie-Generator, um den Server für beständigen Chat Ihren Lync Server 2013-Bereitstellungen hinzuzufügen. Sie können einen oder mehrere Serverpools für beständigen Chat mithilfe des Topologie-Generators hinzufügen. Führen Sie für die Bereitstellung mehrerer Serverpools für beständigen Chat dieselben Bereitstellungsanweisungen wie für einen einzelnen Pool aus. Ausführliche Informationen finden Sie unter [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zu den verfügbaren Topologien, den technischen Anforderungen und den Softwareanforderungen für die Installation von Server für beständigen Chat finden Sie unter [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, unter [Funktionsweise von Persistent Chat Server in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation, und unter [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.

Ausführliche Informationen zum Beziehen von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Dateispeichern finden Sie unter [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

Ein einzelner Server für beständigen Chat- Front-End-Server kann bis zu 20.000 aktive Benutzer unterstützen. Ein Serverpool für beständigen Chat mit bis zu 4 aktiven Front-End-Servern kann insgesamt 80.000 gleichzeitige Benutzer unterstützen.

Server für beständigen Chat wird auch auf einem virtuellen Server unterstützt. Der virtuelle Server kann bis zu 20.000 gleichtzeitige Benutzer unterstützen, wenn er den Spezifikationen des physischen Servers entspricht.


> [!IMPORTANT]
> Zur Erzwingung der Dateisystemsicherheit muss Server für beständigen Chat auf einem NTFS-Dateisystem installiert sein. FAT32 wird für Server für beständigen Chat nicht als Dateisystem unterstützt.



## In diesem Abschnitt

  - [Funktionsweise von Persistent Chat Server in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Prüfliste zur Bereitstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Technische Anforderungen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Einrichten der Systeme und Infrastruktur für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installieren des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Hinzufügen eines Administrators für beständigen Chat in Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Konfigurieren des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Problembehandlung bei der Konfiguration des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Ausführen eines Failovers bzw. Failbacks für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

