---
title: Konfigurieren von unterstützten Clientversionen
TOCTitle: Konfigurieren von unterstützten Clientversionen
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412832(v=OCS.15)
ms:contentKeyID: 49295092
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von unterstützten Clientversionen

 

_**Letztes Änderungsdatum des Themas:** 2012-12-14_

In Lync Server 2013 können Sie Clientversionsrichtlinien einrichten, um die Versionen von Clients anzugeben, die in Ihrer Umgebung unterstützt werden. Darüber hinaus können Sie mithilfe der globalen Clientversionskonfiguration eine Standardaktion für Clients angeben, für die noch keine Versionsrichtlinie definiert ist und die deshalb nicht explizit unterstützt oder eingeschränkt werden.

Sie können auch mithilfe von Clientversionsrichtlinien Clientupdates verwalten. Wenn Sie eine Clientversionsrichtlinie festlegen und die Optionen **Zulassen und Upgrade** und **Blockieren und Upgrade** verwenden, erhalten Clients aktualisierte Software vom Windows Server Update Service (falls Sie diesen Dienst nutzen) oder von Microsoft Update.

## Einstellungen für die Clientversionsrichtlinie

Die standardmäßige Clientversionsrichtlinie erfordert, dass auf allen Clients Lync oder Microsoft Office Communicator 2007 R2 ausgeführt wird. Wenn auf Clients in Ihrer Umgebung frühere Versionen von Communicator ausgeführt werden, müssen Sie die Clientversionsregeln unter Umständen neu konfigurieren. So können Sie verhindern, dass Clients und Geräte unerwartet gesperrt oder aktualisiert werden, wenn eine Verbindung mit Lync Server 2013 hergestellt wird. Sie können entweder die Standardrichtlinie ändern, oder Sie fügen zur Außerkraftsetzung der Standardregel eine Regel hinzu, die in der Liste der Clientversionsrichtlinien höher angeordnet ist. Zusätzlich sollten Sie zur Anwendung neu veröffentlichter kumulativer Updates die Clientversionsrichtlinie so konfigurieren, dass die Anwendung der neuesten Updates erforderlich ist.

