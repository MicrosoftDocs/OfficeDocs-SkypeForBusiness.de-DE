---
title: Verwalten von Quality of Service (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quality of Service (QoS) ist eine Netzwerktechnologie, die in einigen Organisationen verwendet wird, um ein optimales Endbenutzererlebnis für Audio-und Videokommunikation zu gewährleisten.
ms.openlocfilehash: 821ebb1cd6a101856f4fbc4fb3428ecba7674245
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817361"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Verwalten von Quality of Service (QoS) in Skype for Business Server


Quality of Service (QoS) ist eine Netzwerktechnologie, die in einigen Organisationen verwendet wird, um ein optimales Endbenutzererlebnis für Audio-und Videokommunikation zu gewährleisten. QoS wird am häufigsten in Netzwerken verwendet, in denen die Bandbreite begrenzt ist: da eine große Anzahl von Netzwerkpaketen für einen relativ geringen Anteil an verfügbarer Bandbreite konkurrieren, bietet die Dienstqualität eine Möglichkeit für Administratoren, Paketen höhere Prioritäten zuzuweisen. Durchführen von Audio-oder Videodaten. Wenn Sie diesen Paketen eine höhere Priorität geben, werden die Audio-und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechung abgeschlossen, als Netzwerksitzungen, die Dinge wie Dateiübertragungen, Webbrowser oder Datenbanksicherungen betreffen. Das liegt daran, dass für Netzwerkpakete, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden, die Priorität "Best Effort" zugewiesen wird.


> [!NOTE]  
> In der Regel gilt die Dienstqualität nur für Kommunikationssitzungen in Ihrem internen Netzwerk. Wenn Sie QoS implementieren, konfigurieren Sie Ihre Server und Router so, dass die Paket Kennzeichnung unterstützt wird. Sie können diese Geräte jedoch so konfigurieren, dass die Paket Kennzeichnung auf eine bestimmte Weise unterstützt wird. Sie können nicht davon ausgehen, dass die Dienstqualität im Internet oder in anderen Netzwerken unterstützt wird. Auch wenn Quality wenn Service in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass QoS auf die gleiche Weise konfiguriert wird, wie Sie den Dienst in Ihrem Netzwerk konfiguriert haben.

Für Skype for Business Server ist keine Dienstqualität erforderlich; Wenn Sie derzeit keine QoS verwenden, müssen Sie den Dienst vor der Installation von Skype for Business Server nicht installieren. Wenn Sie eine beträchtliche Menge an Paketverlust in Ihrem Netzwerk erleben, empfiehlt es sich, dieses Problem zu beheben, indem Sie zusätzliche Bandbreite hinzufügen. Wenn das Hinzufügen von mehr Bandbreite nicht möglich ist, sollten Sie stattdessen Quality of Service implementieren.

Skype for Business Server bietet umfassende Unterstützung für die Qualität des Diensts: Dies bedeutet, dass Organisationen, die bereits QoS verwenden, Skype for Business Server problemlos in Ihre vorhandene Netzwerkinfrastruktur integrieren können. Dazu müssen Sie die folgenden Aufgaben ausführen:

  - [Aktivieren von QoS für Geräte, die nicht auf Windows basieren](enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Zwar können Sie Skype for Business Server verwenden, um die Dienstqualität für Geräte zu aktivieren und zu deaktivieren, doch können Sie das Produkt in der Regel nicht zum Ändern der DSCP-Codes verwenden, die von diesen Geräten verwendet werden.

  - [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Mit Skype for Business Server können Sie die Dienstqualität nicht aktivieren oder deaktivieren, indem Sie beispielsweise einen Eigenschaftswert auf "wahr" oder "falsch" festlegen. Stattdessen aktivieren Sie die Dienstqualität, indem Sie Portbereiche konfigurieren und dann Gruppenrichtlinien erstellen und anwenden. Wenn Sie sich später entschließen, QoS zu verwenden, können Sie die Qualität des Diensts einfach deaktivieren, indem Sie die entsprechenden Gruppenrichtlinienobjekte entfernen.

  - [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Edgeserver](configuring-port-ranges-for-your-edge-servers.md) Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die der anderen Server konfigurieren. Das Konfigurieren einer Quality of Service-Richtlinie sollte nur für die interne Seite Ihrer Edgeserver erfolgen. Das liegt daran, dass Quality of Service für die Verwendung in Ihrem internen Netzwerk und nicht im Internet vorgesehen ist.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server](configuring-port-ranges-for-your-skype-clients.md)  Diese Portbereiche gelten nur für Clientcomputer und unterscheiden sich in der Regel von den Portbereichen, die auf Ihren Servern konfiguriert sind. Beachten Sie, dass Skype for Business Server keine QoS für Windows-Betriebssysteme außer Windows 10 unterstützt.


