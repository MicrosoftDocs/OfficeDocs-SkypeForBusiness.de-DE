---
title: Verwalten von Quality of Service (QoS)
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quality of Service (QoS) ist eine Netzwerke Technologie, die in einigen Organisationen verwendet wird, um eine optimale benutzerfreundlichkeit für Audio-und Videokommunikation bereitzustellen.
ms.openlocfilehash: 4b75ff3640ec44922176199bdc35d336250a38f9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222905"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Verwalten von Quality of Service (QoS) in Skype für Business Server


Quality of Service (QoS) ist eine Netzwerke Technologie, die in einigen Organisationen verwendet wird, um eine optimale benutzerfreundlichkeit für Audio-und Videokommunikation bereitzustellen. QoS wird am häufigsten verwendet in Netzwerken, wobei Bandbreite begrenzt: mit einer großen Anzahl von Netzwerkpaketen Wettbewerb um relativ wenige der verfügbaren Bandbreite, Quality of Service bietet eine Möglichkeit für Administratoren Pakete höhere Priorität zuweisen Übertragung von Audio- oder Videoinhalten Daten. Erteilen Sie diese Pakete eine höhere Priorität, sind Audio-und Videokommunikation wahrscheinlich schneller und mit weniger als Netzwerk-Sitzungen, die mit Aufgaben wie das dateiübertragungen, das Web durchsuchen oder datenbanksicherungen Unterbrechung abzuschließen. Dies liegt daran Netzwerkpakete für dateiübertragungen oder datenbanksicherungen verwendet eine "best-Effort" Priorität zugewiesen sind.


> [!NOTE]  
> Als allgemeine Regel betrifft Quality of Service nur kommunikationssitzungen im internen Netzwerk. Wenn Sie QoS implementieren, konfigurieren Sie die Server und Router zur Unterstützung von Paket markieren; Allerdings konfigurieren Sie diese Geräte zur Unterstützung der Markierung in einer bestimmten Weise Paket. Sie können nicht annehmen, dass Quality of Service im Internet oder in anderen Netzwerken unterstützt wird. Auch bei Qualität Wenn Dienst, in anderen Netzwerken unterstützt wird konfiguriert keine Garantie dafür gibt, die QoS werden die gleiche Weise, dass Sie den Dienst in Ihrem Netzwerk konfiguriert haben.

Skype für Business Server erfordert keine Quality of Service. Wenn Sie derzeit nicht QoS verwenden ist es nicht erforderlich, dass Sie den Dienst vor der Installation von Skype für Business Server installieren. Wenn Sie eine beträchtliche Paketverlust in Ihrem Netzwerk empfohlen, dieses Problem zu beheben auftreten werden zusätzliche Bandbreite hinzugefügt. Wenn mehr Bandbreite hinzufügen nicht möglich ist, sollten Sie stattdessen implementieren Quality of Service.

Skype für Business Server bietet umfassende Unterstützung für Quality of Service:, dass bedeutet, die Organisationen, die bereits QoS verwenden auf einfache Weise können Skype für Business Server in ihrer vorhandenen Infrastruktur integrieren. Zu diesem Zweck müssen Sie die folgenden Aufgaben ausführen:

  - [Aktivieren von QoS für Geräte, die nicht auf Windows basieren](enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Kann zwar Skype für Business Server aktivieren und Deaktivieren von Quality of Service für Geräte, in der Regel können das Produkt Sie um die DSCP-Codes verwendet, die für diese Geräte zu ändern.

  - [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendung und Mediation Server](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Mit Skype für Business Server führen Sie Sie nicht aktivieren oder deaktivieren Quality of Service, beispielsweise einen Eigenschaftswert auf True oder auf False festlegen. Stattdessen können Sie Quality of Service durch Konfigurieren von Portbereichen und erstellen und Anwenden von Gruppenrichtlinien. Wenn Sie später entscheiden, nicht zu QoS verwenden können Sie "Quality of Service deaktivieren", indem Sie einfach die entsprechenden Gruppenrichtlinienobjekte zu entfernen.

  - [Konfigurieren von Portbereichen und einer Richtlinie Quality of Service für Edge-Server](configuring-port-ranges-for-your-edge-servers.md). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die der anderen Server konfigurieren. Konfigurieren einer QoS-Richtlinie sollte nur für die interne Seite des Edge-Server ausgeführt werden. Dies liegt daran Quality of Service für die Verwendung in Ihrem internen Netzwerk und nicht auf das Internet entwickelt wurde.

- [Konfigurieren von Portbereichen und einer Richtlinie Quality of Service für Clients in Skype für Business Server](configuring-port-ranges-for-your-skype-clients.md)  Diese Portbereiche gelten nur für Clientcomputer und unterscheiden sich in der Regel von die Portbereiche auf Ihren Servern konfiguriert. Beachten Sie, dass Skype für Business Server QoS für Windows-Betriebssysteme als Windows 10 nicht unterstützt.


