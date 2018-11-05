---
title: 'Lync Server 2013: Konfigurieren der automatischen Clientanmeldung zur Verwendung des Directors'
TOCTitle: Konfigurieren der automatischen Clientanmeldung zur Verwendung des Directors
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398678(v=OCS.15)
ms:contentKeyID: 49294629
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der automatischen Clientanmeldung zur Verwendung des Directors in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Wenn Sie einen Lync Server 2013-Director oder -Director-Pool bereitstellen, wird die Verwendung der automatischen Clientanmeldung empfohlen. Ausführliche Informationen zur Konfiguration von DNS-Servern für die automatische Clientanmeldung finden Sie unter [DNS-Anforderungen für die automatische Clientanmeldung](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in der Planungsdokumentation.

Wenn Sie die automatische Clientanmeldung bereits bereitgestellt haben, finden Sie in den folgenden Abschnitten Informationen zur Konfiguration dieser Funktion für Ihre Director-Server.

## Einzelne Director-Instanz

Wenn Sie die automatische Clientanmeldung bereits bereitgestellt haben und diese auf einen Front-End-Server oder einen Front-End-Pool zeigt, müssen Sie den DNS-SRV-Eintrag so ändern, dass dieser auf den Director zeigt.

## Director-Pool

Wenn Sie die automatische Clientanmeldung bereits bereitgestellt haben und diese auf einen Front-End-Server oder einen Front-End-Pool zeigt, müssen Sie den DNS-SRV-Eintrag so ändern, dass dieser auf den Director-Pool zeigt.

