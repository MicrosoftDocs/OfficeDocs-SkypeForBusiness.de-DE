---
title: Ersetzen des XmlAdapter durch einen angepassten Kompatibilitätsadapter für Persistent Chat Server in Lync Server 2013
TOCTitle: Ersetzen des XmlAdapter durch einen angepassten Kompatibilitätsadapter für Persistent Chat Server in Lync Server 2013
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49890681
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ersetzen des XmlAdapter durch einen angepassten Kompatibilitätsadapter für Persistent Chat Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Sie können einen benutzerdefinierten Adapter schreiben, anstatt den mit Server für beständigen Chat installierten XmlAdapter zu verwenden. Hierzu müssen Sie eine .NET Framework-Assembly bereitstellen, die eine öffentliche Klasse enthält, die die **IComplianceAdapter**-Schnittstelle implementiert. Sie müssen diese Assembly in den Server für beständigen Chat-Installationsordner auf jedem Server im Serverpool für beständigen Chat einfügen. Jeder der Konformitätsserver kann Konformitätsdaten für Ihren Adapter bereitstellen, aber die Konformitätsserver stellen keine doppelten Konformitätsdaten für mehrere Instanzen des Adapters bereit.

## Implementieren der IComplianceAdapter-Schnittstelle

Die Schnittstelle wird in der Assembly **Compliance.dll** im Namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance` definiert. Die Schnittstelle definiert zwei Methoden, die Ihr benutzerdefinierter Adapter implementieren muss.

    void SetConfig(AdapterConfig config)

Der Beständiger Chat-Konformitätsserver ruft diese Methode auf, wenn der Adapter erstmals geladen wird. Der `AdapterConfig` enthält die Beständiger Chat-Konformitätskonfiguration, die für den Konformitätsadapter relevant ist.

    void Translate(ConversationCollection conversations)

Der Beständiger Chat-Konformitätsserver ruft diese Methode in regelmäßigen Abständen auf, sofern neue zu übersetzende Daten vorhanden sind. Dieses Zeitintervall entspricht dem `RunInterval`, so wie in der Beständiger Chat-Konformitätskonfiguration festgelegt.

`ConversationCollection` enthält die Unterhaltungsinformationen, die beim letzten Aufruf dieser Methode gesammelt wurden.

