---
title: Definieren des Umfangs der E9-1-1-Bereitstellung in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Entscheidungen zur Planung einer E9-1-1-bereitstellungs in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 014ef9a07679341a7d5eada4ecbad382a9576b61
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206480"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definieren des Umfangs der E9-1-1-Bereitstellung in Skype für Business Server

Entscheidungen zur Planung einer E9-1-1-bereitstellungs in Skype für Business Server Enterprise-VoIP.

Bevor Sie Skype für Unternehmen für E9-1-1 konfigurieren, müssen Sie die E9-1-1-Bereitstellung zu planen. Stellen Sie sich die folgenden Fragen:

 **Was sind Richtlinien und Vorschriften in Bezug auf E9-1-1 Ihrer Organisation?**

 Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als „Telefonsysteme mit mehreren Leitungen“ oder „Mehrleitungstelefonsysteme“ bezeichnet) unterscheiden sich von Staat zu Staat. Sie sollten wenden Sie sich mit Ihrem Team rechtlichen, die Verpflichtungen zu verstehen, die für die Bereitstellung von Skype für Unternehmen in die entsprechenden Regionen gelten.

 **Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**

 Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten und Standorte außerhalb der USA können ausgeschlossen werden.

 **Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**

 Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen. Wenn Sie E-9-1-1-SIP-Trunks zentral haben, und ein WAN-Ausfalls auftritt, Clients anmelden zum Abrufen eines Speicherorts aus standortinformationsdienst oder die Verbindung mit dem Dienstanbieter Notdienste möglicherweise nicht. Skype für Unternehmen bietet mehrere Strategien für die Verarbeitung von VoIP-ausfallsicherheit in Zweigstellen, einschließlich: müssen ausfallsichere Datennetzwerke, einen SIP-Trunk in jeder Zweigstelle bereitstellen oder pushen von Notrufen an das lokale Gateway out bei Ausfällen. Ausführliche Informationen finden Sie unter [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**

 Automatische Speicherort Erwerb steht nur für Clients, die im Netzwerk der Organisation, damit Ihre Organisation muss entscheiden, ob sie E9-1-1-Anrufe zwischen Skype für Clients während der lokale-Business unterstützen. Beispielsweise können Sie Benutzer Notrufe tätigen, wenn sie von zu Hause oder aus einem Kundenstandort arbeiten? Wenn ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client konfiguriert werden, um einen Speicherort für den Benutzer aufzufordern. Da diese Benutzer bereitgestellten Speicherorte gegen Master Street Address Guide (Street) prevalidated ist nicht möglich, wird der emergency Services Service Provider Verteiler müssen jedoch die Gültigkeit des Speicherorts Alternativtext mit dem Anrufer vor dem routing bestätigen der Anruf an öffentliche Sicherheit beantworten Point (PSAP).

> [!NOTE]
> Skype für Business-Clients der Benutzer über VPN eine Verbindung mit Netzwerk Ihrer Organisation herstellen kann interne IP-Adressinformationen aufzunehmen, aber, da diese Adressen zum Identifizieren der aktuelle Standort des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze ausgeschlossen werden aus dem Dienst Standortinformationen.

 **Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**

 Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter einer Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird, VoIP-Richtlinien zu.


