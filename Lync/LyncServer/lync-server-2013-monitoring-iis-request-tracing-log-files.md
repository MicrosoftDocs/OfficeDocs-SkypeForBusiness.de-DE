---
title: Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen
TOCTitle: Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690034(v=OCS.15)
ms:contentKeyID: 49295167
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wenn Sie die Internetinformationsdienste (Internet Information Services, IIS)-Ablaufverfolgung für Anforderungen für den Lync Server Mobilitätsdienst aktivieren, können die generierten Protokolldateien bis zu drei Gigabytes Speicherplatz pro Tag belegen. Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert. Sie sollten die Front-End-Server überwachen, um sicherzustellen, dass der Speicherplatz nicht zur Neige geht.

Standardmäßig werden die Protokolldateien von Internetinformationsdienste (IIS) unter "%SystemDrive%\\inetpub\\logs\\LogFiles" gespeichert.

Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Ausführliche Informationen zum Befehl **httpLogging** finden Sie unter [http://go.microsoft.com/fwlink/?linkid=234927\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=234927%26clcid=0x407).

