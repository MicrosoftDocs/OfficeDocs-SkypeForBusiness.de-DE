---
title: Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server
TOCTitle: Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server
ms:assetid: 5b4d3db1-6eba-4932-b49c-f60bcf9488f9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615442(v=OCS.15)
ms:contentKeyID: 49294114
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Die Themen in diesem Abschnitt begleiten Sie bei der Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2Gruppenchat zu Lync Server 2013Server für beständigen Chat. Wenn Sie Ihre Lync Server 2013Server für beständigen Chat-Bereitstellung gemeinsam mit einer Lync Server 2010-Gruppenchat- oder Office Communications Server 2007 R2Gruppenchat-Bereitstellung verwenden möchten, erhalten Sie in diesem Leitfaden auch einige grundlegende Informationen für den Betrieb in einer solchen gemischten Umgebung. Im Mittelpunkt dieses Leitfadens steht jedoch die Datenmigration für Server für beständigen Chat. Benutzer, die eine Migration von älteren Lync Server-Versionen zu Lync Server 2013 durchführen, erhalten unter [Migration von Lync Server 2010 zu Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) und [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) weitere Informationen.


> [!IMPORTANT]
> In diesem Thema wird davon ausgegangen, dass Sie Lync Server 2013 bereits zusammen mit Lync Server 2010 oder Office Communications Server 2007 R2 installiert haben.




> [!IMPORTANT]
> In diesem Leitfaden werden die Schritte beschrieben, die im Allgemeinen zur Durchführung der einzelnen Phasen der Migration erforderlich sind. Es wird darin nicht auf jede mögliche Bereitstellungstopologie der Vorversion oder jedes mögliche Migrationsszenario eingegangen. Deshalb ist es nicht notwendig, dass Sie jeden beschriebenen Schritt ausführen. Möglicherweise müssen Sie auch, abhängig von Ihrer Bereitstellung, zusätzliche Schritte ausführen. Darüber hinaus werden in diesem Leitfaden auch Beispiele für Überprüfungsschritte aufgeführt. Durch diese Überprüfungsschritte können Sie einfacher erkennen, wie Sie die erfolgreiche Ausführung der einzelnen Phasen der Migration sicherstellen können. Passen Sie diese Überprüfungsschritte bei Bedarf an Ihren jeweiligen Migrationsprozess an.



Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Dieses Handbuch enthält entsprechende Verweise auf Verfahren, die in anderen Dokumenten detailliert beschrieben sind.

In diesem Dokument werden Begriffe gemäß der Definition in der folgenden Liste verwendet.

  - *Migration*   
    Verschieben der Bereitstellung von einer Vorversion von Server für beständigen Chat (früher als Gruppenchatserver bezeichnet) zu Lync Server 2013, Server für beständigen Chat.

<!-- end list -->

  - *Upgrade*   
    Installieren einer neueren Softwareversion auf einem Server oder Clientcomputer.

<!-- end list -->

  - *Koexistenz*   
    Die temporäre Umgebung während der Migration, wenn einige Funktionen zu Lync Server 2013Server für beständigen Chat migriert wurden, während andere Funktionen noch von einer Vorversion von Gruppenchatserver bereitgestellt werden.

Server für beständigen Chat ist eine Erweiterung der Lync Server 2013-Infrastruktur. In Abhängigkeit von Ihrer Topologie können Sie Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2Gruppenchat zu einem Lync Server 2013Server für beständigen Chat migrieren. Ausführliche Informationen zu den verfügbaren Topologien, den technischen Anforderungen und den Softwareanforderungen für die Migration von Gruppenchatserver finden Sie in der Planungsdokumentation unter [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, wird diese jetzt automatisch mit jedem Server für beständigen Chat installiert. Eine separater Kompatibilitätsserver ist nicht mehr erforderlich.


> [!IMPORTANT]
> Zur Erzwingung der Dateisystemsicherheit muss Server für beständigen Chat auf einem NTFS-Dateisystem installiert sein. FAT32 wird für Server für beständigen Chat nicht als Dateisystem unterstützt.<BR>Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, wird diese jetzt automatisch mit jedem Server für beständigen Chat installiert. Eine separater Kompatibilitätsserver ist nicht mehr erforderlich. Nähere Informationen zu den Änderungen in der Dokumentation "Erste Schritte" unter Lync Server 2013Server für beständigen Chat finden Sie unter <A href="lync-server-2013-new-persistent-chat-server-features.md">Neue Funktionen für den Server für beständigen Chat in Lync Server 2013</A>.



## In diesem Abschnitt

  - [Standardmigrationsszenario – Übersicht](standard-migration-scenario-high-level.md)

  - [Migrationsprozess – Details](migration-process-details.md)

  - [Überlegungen zur Koexistenz](coexistence-considerations.md)

