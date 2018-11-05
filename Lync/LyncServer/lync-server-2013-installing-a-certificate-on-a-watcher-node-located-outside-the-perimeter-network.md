---
title: Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet
TOCTitle: Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49890819
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für System Center Operations Manager-Agents, die in einem Umkreisnetzwerk (z. B. ein Lync Server-Edgeserver), außerhalb des Unternehmens (z. B. ein externer Watcher-Knoten für synthetische Transaktionen) ober über eine Active Directory-Domänendienste-Vertrauensstellungsgrenze ausgeführt werden, muss möglicherweise ein System Center Operations Manager Gateway Server konfiguriert werden. Diese Serverrolle ermöglicht es Agents, die keine Vertrauensstellung mit dem Root Management Server haben, Warnungen auszulösen. Ausführliche Informationen finden Sie in "Verwalten von Gatewayservern in Operations Manager 2007" in der System Center Operations Manager-TechNet-Bibliothek unter [http://go.microsoft.com/fwlink/?linkid=268703\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268703%26clcid=0x407).

Wenn Sie einen Agent an einem dieser Standorte bereitstellen, müssen Sie ein Zertifikat anfordern und konfigurieren, mit dem der Watcher-Knoten Warnungen an System Center Operations Manager senden kann. Um dieses Verfahren zu vereinfachen, hat das Operations Manager-Team eine Reihe an Dienstprogrammen erstellt, mit denen Sie den richtigen Typ des Zertifikats anfordern und auf dem Computer mit dem Watcher-Knoten installieren können. Ausführliche Informationen, unter anderem zum Herunterladen dieser Dienstprogramme, finden Sie im Blog-Artikel "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" unter [http://go.microsoft.com/fwlink/?linkid=267421\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=267421%26clcid=0x407).

