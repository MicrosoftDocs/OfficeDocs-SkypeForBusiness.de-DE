---
title: Bereitstellen von Lync-Clients
TOCTitle: Bereitstellen von Lync-Clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204827(v=OCS.15)
ms:contentKeyID: 49293751
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Lync-Clients

 

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Lync 2013 führt einen anderen Ansatz zur Client-Bereitstellung ein. Im Unterschied zu früheren Versionen gibt es bei Lync 2013 kein eigenes Installationsprogramm mehr. Stattdessen verfügt Lync über das Office 2013-Setupprogramm. Zur Bereitstellung von Lync 2013 für Ihre Benutzer können Sie Installationsmethoden und Anpassungstools von Office 2013 verwenden.

  - **Der Windows Installer für Office 2013** ist ein auf Windows Installer basierendes Installationspaket, das aus mehreren MSI-Dateien besteht. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus. In den Themen in diesem Abschnitt wird beschrieben, wie der Windows Installer für Office 2013 zur Bereitstellung von Lync 2013 verwendet und angepasst werden kann.

  - **Office 2013 Klick-und-Los** ist ein Installationsprogramm, das Office-Setupdateien vom Microsoft Office 365-Portal an die Benutzer streamt. Administratoren können die Installation anpassen, indem sie das Office-Bereiststellungstool für Klick-und-Los verwenden. Da Office 2013 Klick-und-los hauptsächlich in der Microsoft Office 365-Umgebung verwendet wird, ist diese Installationsmethode in diesem Abschnitt nicht ausführlich beschrieben. Ausführliche Informationen zur Verwendung und Anpassung der Klick-und-Los-Installation finden Sie in der Dokumentation zum Office 2013 Resource Kit. Administratoren können außerdem das Office 2013 Klick-und-Los-Programm und die Sprachquelldateien in einen lokalen Speicherort herunterladen. Dies ist hilfreich, wenn Sie die Netzwerkauslastung minimieren oder aufgrund von Anforderungen der Unternehmenssicherheit verhindern möchten, dass Benutzer Software aus dem Internet installieren.

Die Themen in diesem Abschnitt konzentrieren sich darauf, wie Clients mithilfe des MSI-basierten Office 2013-Installationsprogramms bereitgestellt werden können. Ihre primäre Referenz sollte die Dokumentation zum Office 2013 Resource Kit sein. Dort ist ausführlich beschrieben, wie Sie Ihre Infrastruktur vorbereiten, Setup anpassen und Office 2013 bereitstellen können. Sie sollten die Office-Dokumentation jedoch in Verbindung mit den Themen in diesem Abschnitt verwenden, da diese auf spezifische Bereitstellungsaspekte für Lync 2013 eingehen.


> [!NOTE]
> <UL>
> <LI>
> <P>Das Onlinebesprechungs-Add-In für Lync&nbsp;2013, das die Besprechungsverwaltung aus dem Outlook-Client für Messaging und Zusammenarbeit unterstützt, wird automatisch mit Lync 2013 installiert.</P>
> <LI>
> <P>Das Office 2013-Setupprogramm deinstalliert vorige Versionen von Lync oder Office Communicator nicht. Der Lync 2013-Client wird parallel zu anderen Lync- oder Office Communicator-Clients installiert.</P></LI></UL>



## Inhalt dieses Abschnitts

  - [Anpassen einer Clientinstallation](lync-server-2013-customizing-client-installation.md)

  - [Anpassen des Verhaltens und der Benutzeroberfläche von Lync](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Anpassen des Onlinebesprechungs-Add-Ins](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Konfigurieren von unterstützten Clientversionen](lync-server-2013-configuring-supported-client-versions.md)

  - [Konfigurieren des erweiterten Datenschutzmodus für Anwesenheitsinformationen](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

