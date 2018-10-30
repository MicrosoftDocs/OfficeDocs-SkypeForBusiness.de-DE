---
title: Topologien für IP-Telefone
TOCTitle: Topologien für IP-Telefone
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425740(v=OCS.15)
ms:contentKeyID: 49293472
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologien für IP-Telefone

 

_**Letztes Änderungsdatum des Themas:** 2012-06-21_

In diesem Abschnitt erhalten Sie einen Überblick über den Prozess der Verbindungsherstellung. Erklärt werden außerdem die Unterschiede zwischen dem Herstellen einer Verbindung über ein IP-Telefon in einem internen Netzwerk und dem gleichen Vorgang in einem externen Netzwerk.


> [!NOTE]
> Lync Server unterstützt die folgenden IP-Telefone: Aastra 6721ip IP-Telefon für öffentliche Bereiche, Aastra 6725ip Tischtelefon, HP 4110 IP-Telefon für öffentliche Bereiche, HP 4120 IP-Telefon (Tischtelefon), Polycom CX600 IP-Tischtelefon, Polycom CX700 IP-Tischtelefon, Polycom CX500 IP-Telefon für öffentliche Bereiche und Polycom CX3000 IP-Konferenztelefon. Bis auf Polycom CX700 kann auf allen Telefonen Lync Phone Edition ausgeführt werden.



Im folgenden Diagramm werden alle Komponenten beschrieben, die an der Geräteanbindung innerhalb einer Unternehmensumgebung beteiligt sind.

**Interne Topologie**

![Geräte im Netzwerk](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "Geräte im Netzwerk")


> [!NOTE]
> Die obige Abbildung ist eine logische Darstellung und keine physische. Beispielsweise wird sich Active Directory-Domänendienste (Active Directory Domain Services, AD DS) in den seltensten Fällen auf dem gleichen Computer befinden wie Lync Server-Komponenten. Der Benutzerspeicher kann sich auf dem Back-End-Server oder auf den Archivierungs- und Monitoring Servern befinden. Die Lync Server-Verwaltungsshell, der Webserver und die Updatedienste sind alle Bestandteil der Front-End-Serverrolle.



Das folgende Diagramm zeigt einen Überblick über die Komponenten, die beteiligt sind, wenn das Gerät sich außerhalb des Unternehmensnetzwerks befindet.

**Externe Topologie**

![Geräte außerhalb des Netzwerks](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "Geräte außerhalb des Netzwerks")


> [!NOTE]
> Der Geräteupdate-Webdienst stellt eine externe und eine interne Website bereit, hier wird jedoch nur die externe gezeigt.<BR>Der Standort der Registrierungsstelle und die URL des Geräteupdate-Webdiensts für die Organisation müssen in DNS veröffentlicht werden, wenn Zugriff durch externe Benutzer unterstützt werden soll. Außerdem muss der Edgeserver bereitgestellt und korrekt konfiguriert werden, damit externe Kommunikation vom Gerät zur Unternehmensumgebung und zurück möglich ist. Dies wird im obigen Diagramm nicht dargestellt, da die Edgebereitstellung nicht spezifisch für die Geräteanbindung ist.


