---
title: 'Lync Server 2013: Schützen von Daten während der Übertragung – Archivierungs-, Überwachungs- und Gruppenchat-Konformitätsserverdatenbanken'
TOCTitle: Schützen von Daten während der Übertragung – Archivierungs-, Überwachungs- und Gruppenchat-Konformitätsserverdatenbanken in Lync Server 2013
ms:assetid: ea219705-1015-43a7-890b-e7e67b451e7c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn518336(v=OCS.15)
ms:contentKeyID: 60476350
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schützen von Daten während der Übertragung – Archivierungs-, Überwachungs- und Gruppenchat-Konformitätsserverdatenbanken in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync Server 2013 Monitoring Server und der Archivierungsserver verwenden beide den Message Queuing-Dienst (der auch als MSMQ bezeichnet wird), um Datennachrichten zu erfassen und zuverlässig vom Auflistungspunkt zu den Repositoryservern zu verschieben. Der Konformitätsdienst erfasst Daten zusammen mit dem Gruppenchatserver, der ebenfalls Message Queuing verwendet.

In Lync Server 2013 gibt es keinen internen Schutz für Daten, die über das Netzwerk übertragen werden. Wenn jedoch die Anforderung besteht, diesen Datenverkehr zu sichern, kann der Message Queuing-Dienst eine Verschlüsselung auf der Nachrichtenebene in der sendenden Nachrichtenwarteschlenge bereitstellen. Dies wird über die Verwendung von Zertifikaten erreicht, die von den Active Directory-Verbunddiensten verwaltet werden. Ausführliche Informationen finden Sie in "Anhang D: Message Queuing und Internetkommunikation unter Windows Server 2008" unter [http://go.microsoft.com/fwlink/p/?LinkId=145238](http://go.microsoft.com/fwlink/p/?linkid=145238) oder "Anhang I: Message Queuing und Internetkommunikation unter Windows Server 2008 R2" unter [http://go.microsoft.com/fwlink/p/?LinkId=211883](http://go.microsoft.com/fwlink/p/?linkid=211883) für Windows Server 2008 R2.

