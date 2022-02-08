---
title: Verwalten der Dienstqualität (Quality of Service, QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Bei der Dienstqualität (Quality of Service, QoS) handelt es sich um eine Netzwerktechnologie, die in einigen Organisationen zum Bereitstellen einer optimalen Benutzerfreundlichkeit für die Audio- und Videokommunikation verwendet wird.
ms.openlocfilehash: 043d29eea849ffbd534199a6622b35e2322f7044
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390117"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Verwalten von Quality of Service (QoS) in Skype for Business Server


Bei der Dienstqualität (Quality of Service, QoS) handelt es sich um eine Netzwerktechnologie, die in einigen Organisationen zum Bereitstellen einer optimalen Benutzerfreundlichkeit für die Audio- und Videokommunikation verwendet wird. QoS kommt am häufigsten in Netzwerken mit beschränkter Bandbreite zum Einsatz, bei denen eine große Anzahl Netzwerkpakete um eine relativ geringe Bandbreite konkurrieren, Die Dienstqualität stellt für Administratoren eine Möglichkeit dar, um Paketen mit Audio- oder Videodaten höhere Prioritäten zuzuweisen. Durch die Zuweisung einer höheren Priorität zu diesen Paketen kann die Audio- und Videokommunikation schneller und mit weniger Unterbrechungen ausgeführt werden als Netzwerksitzungen, in denen Dateiübertragungen, Webbrowsen oder Datenbanksicherungen erfolgen. Die Ursache dafür ist die Zuweisung einer "Best Effort"-Priorität zu den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden.


> [!NOTE]  
> In der Regel wird die Dienstqualität nur auf Kommunikationssitzungen innerhalb Ihres internen Netzwerks angewendet. Beim Implementieren von QoS konfigurieren Sie die Server und Router zwar für die Unterstützung der Paketmarkierung, Sie konfigurieren diese Geräte jedoch für die Unterstützung der Paketmarkierung auf eine bestimmte Art und Weise. Sie können nicht davon ausgehen, dass die Dienstqualität im Internet oder in anderen Netzwerken unterstützt wird. Selbst wenn die Dienstqualität in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass sie auf dieselbe Art und Weise wie der Dienst in Ihrem Netzwerk konfiguriert ist.

Skype for Business Server erfordert keine Dienstqualität. Wenn Sie QoS derzeit nicht verwenden, ist es nicht erforderlich, den Dienst vor der Installation von Skype for Business Server zu installieren. Wenn in Ihrem Netzwerk ein erheblicher Paketverlust auftritt, empfiehlt es sich, dieses Problem zu verringern, indem Sie zusätzliche Bandbreite hinzufügen. Wenn das Hinzufügen von mehr Bandbreite nicht möglich ist, sollten Sie stattdessen Quality of Service implementieren.

Skype for Business Server bietet vollständige Unterstützung für Quality of Service: Das bedeutet, dass Organisationen, die QoS bereits verwenden, Skype for Business Server problemlos in ihre vorhandene Netzwerkinfrastruktur integrieren können. Dazu müssen Sie die folgenden Aufgaben ausführen:

  - [Aktivieren von QoS für Geräte, die nicht auf Windows basieren](enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Obwohl Sie Skype for Business Server verwenden können, um Quality of Service für Geräte zu aktivieren und zu deaktivieren, können Sie das Produkt in der Regel nicht verwenden, um die von diesen Geräten verwendeten DSCP-Codes zu ändern.

  - [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Bei Skype for Business Server aktivieren oder deaktivieren Sie Quality of Service nicht, indem Sie beispielsweise einen Eigenschaftswert auf "True" oder "False" festlegen. Stattdessen wird die Dienstqualität durch die Konfiguration von Portbereichen und die anschließende Erstellung und Anwendung einer Gruppenrichtlinie aktiviert. Wenn Sie sich später dazu entschließen, QoS nicht zu verwenden, können Sie die Dienstqualität einfach durch Entfernen der entsprechenden Gruppenrichtlinienobjekte "deaktivieren".

  - [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Edgeserver](configuring-port-ranges-for-your-edge-servers.md). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die anderen Server konfigurieren. Das Konfigurieren einer Quality of Service-Richtlinie sollte nur für die interne Seite Ihrer Edgeserver erfolgen. Die Ursache dafür ist, dass die Dienstqualität nicht für die Verwendung im Internet, sondern in Ihrem internen Netzwerk konzipiert ist.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server](configuring-port-ranges-for-your-skype-clients.md) Diese Portbereiche gelten nur für Clientcomputer und unterscheiden sich in der Regel von den auf Ihren Servern konfigurierten Portbereichen. Beachten Sie, dass Skype for Business Server QoS nicht für andere Windows betriebssysteme als Windows 10 unterstützt.


