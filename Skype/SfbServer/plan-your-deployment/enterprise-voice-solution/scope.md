---
title: Definieren des Bereichs der E9-1-1-Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Entscheidungen, die für die Planung einer E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind.
ms.openlocfilehash: fa300ac2f4ba1c0d847abec138b6882e4f240831
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802465"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definieren des Bereichs der E9-1-1-Bereitstellung in Skype for Business Server

Entscheidungen, die für die Planung einer E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind.

Bevor Sie Skype for Business für E9-1-1 konfigurieren, müssen Sie Ihre E9-1-1-Bereitstellung planen. Stellen Sie sich die folgenden Fragen:

 **Was sind die Richtlinien und rechtlichen Verpflichtungen Ihrer Organisation in Bezug auf E9-1-1?**

 Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als „Telefonsysteme mit mehreren Leitungen“ oder „Mehrleitungstelefonsysteme“ bezeichnet) unterscheiden sich von Staat zu Staat. Wenden Sie sich an ihr rechtliches Team, um sich mit den Verpflichtungen vertraut zu machen, die für Ihre Bereitstellung von Skype for Business in ihren relevanten Regionen gelten können.

 **Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**

 Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten und Standorte außerhalb der USA können ausgeschlossen werden.

 **Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**

 Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen. Wenn Sie über zentralisierte E-9-1-1-SIP-Trunks verfügen und ein WAN-Ausfall auftritt, können Clients, die sich anmelden, möglicherweise keinen Standort vom standortinformationsdienst abrufen oder eine Verbindung mit dem Notdienste-Dienstanbieter herstellen. Skype for Business bietet verschiedene Strategien für die Behandlung von sprach Stabilität in Zweigniederlassungen, darunter: robustes Daten Netz, Bereitstellungeines SIP-Trunks an jedem Zweig oder Pushen von Notrufen beim Ausfall des lokalen Gateways. Ausführliche Informationen finden Sie unter [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**

 Die automatische Standorterfassung steht nur für Clients zur Verfügung, die sich im Netzwerk der Organisation befinden, sodass Ihre Organisation entscheiden muss, ob Sie E9-1-1-Anrufe unterstützt, die von Skype for Business-Clients außerhalb des Lokals getätigt werden. Möchten Sie beispielsweise Benutzern die Möglichkeit geben, Notrufe zu tätigen, wenn Sie von zu Hause oder von einem Kundenstandort aus arbeiten? Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client so konfiguriert werden, dass er den Benutzer zur Eingabe eines Speicherorts auffordert. Da diese vom Benutzer bereitgestellten Speicherorte jedoch nicht mit dem Master Street Address Guide (MSAG) vorab validiert werden können, muss der Dienstanbieter für Notrufdienste die Gültigkeit des Standorts mit dem Anrufer vor dem Routing bestätigen. der Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP).

> [!NOTE]
> Skype for Business-Clients von Benutzern, die mithilfe von VPN eine Verbindung mit dem Netzwerk Ihrer Organisation herstellen, können interne IP-Adressinformationen aufnehmen, aber da diese Adressen nicht zur Identifizierung des tatsächlichen Standorts des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze ausgeschlossen werden. vom standortinformationsdienst aus.

 **Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**

 Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter einer Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird, VoIP-Richtlinien zu.


