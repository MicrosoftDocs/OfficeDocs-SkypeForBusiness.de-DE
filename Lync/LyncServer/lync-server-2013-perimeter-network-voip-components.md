---
title: 'Lync Server 2013: VoIP-Komponenten für das Umkreisnetzwerk'
TOCTitle: VoIP-Komponenten für das Umkreisnetzwerk
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398559(v=OCS.15)
ms:contentKeyID: 49294423
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoIP-Komponenten für das Umkreisnetzwerk für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Externe Anrufer, die Unified Communications-Clients für Einzelgespräche oder Telefonkonferenzen verwenden, nutzen Edgeserver für die Sprachkommunikation mit Kollegen.

Auf einem Edgeserver stellt der Zugriffs-Edgedienst SIP-Signaldaten für Anrufe von Benutzern von Lync bereit, die sich außerhalb der Unternehmensfirewall befinden. Der A/V-Edgedienst ermöglicht es Medien Firewalls und NAT zu passieren. Anrufer, die einen Unified Communications-Client (UC) außerhalb der Unternehmensfirewall verwenden, benötigen den A/V-Edgedienst für Einzelgespräche und Telefonkonferenzen.

Der A/V-Authentifizierungsdienst ist mit dem A/V-Edgedienst verknüpft und stellt Authentifizierungsdienste für ihn bereit. Externe Benutzer, die versuchen, eine Verbindung mit dem A/V-Edgedienst herzustellen, benötigen ein vom A/V-Authentifizierungsdienst bereitgestelltes Authentifizierungstoken, damit ihre Anrufe durchgestellt werden können.

