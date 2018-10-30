---
title: 'Lync Server 2013: Neue Trunkfunktion'
TOCTitle: Neue Trunkfunktion
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49890861
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue Trunkfunktion in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In Microsoft Lync Server 2013 können zwischen einem Vermittlungsserver und einem Gateway mehrere Trunks definiert werden. Microsoft Lync Server 2010 hat nur einen Trunk zwischen einem Vermittlungsserver und einem PSTN-Gateway zugelassen. Diese Funktion bietet die Flexibilität, zusätzliche Trunks zu definieren. Ein Trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver-FQDN mit Überwachungsport und einem PSTN-Gateway-FQDN mit Überwachungsport. Diese neue Möglichkeit erlaubt eine einfache Trunkdefinition für Resilienz (mehrere Vermittlungsserver können für das Weiterleiten von Anrufen an dasselbe PSTN-Gateway genutzt werden), für Interoperabilität mit Nebenstellenanlagen, indem mehrere Trunks mit unterschiedlicher Richtlinienzuordnung zwischen einer IP-Nebenstellenanlage und einem Vermittlungsserver verwendet werden können, sowie für SIP-Trunkkonfigurationen, bei denen Vermittlungsserver an verschiedenen Standorten SIP-Trunks für den durch denselben Netzbetreiber-FQDN referenzierten Netzbetreiber verwenden.

## Siehe auch

#### Konzepte

[Neue Enterprise-VoIP-Funktionen in Lync Server 2013](lync-server-2013-new-enterprise-voice-features.md)

