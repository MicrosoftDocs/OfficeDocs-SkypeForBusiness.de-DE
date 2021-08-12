---
title: Definieren des Umfangs der E9-1-1-Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 0fb334f612c2e63a7c2e47779ee4f02ee0e543741a460933cb632bdd8e54d279
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290063"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definieren des Umfangs der E9-1-1-Bereitstellung in Skype for Business Server

Entscheidungen, die für die Planung einer E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind.

Bevor Sie Skype for Business für E9-1-1 konfigurieren, müssen Sie Ihre E9-1-1-Bereitstellung planen. Stellen Sie sich die folgenden Fragen:

 **Was sind die Richtlinien und gesetzlichen Verpflichtungen Ihrer Organisation in Bezug auf E9-1-1?**

 Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als "Telefonsysteme mit mehreren Leitungen" oder "Mehrleitungstelefonsystemen" bezeichnet) unterscheiden sich von Staat zu Staat. Wenden Sie sich an Ihr Rechtsteam, um die Verpflichtungen zu verstehen, die für die Bereitstellung von Skype for Business in Ihren relevanten Regionen gelten können.

 **Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**

 Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten, und Standorte außerhalb der USA können ausgeschlossen werden.

 **Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**

 Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen. Wenn Sie über zentralisierte E-9-1-1-SIP-Trunks verfügen und ein WAN-Ausfall auftritt, können sich anmeldende Clients möglicherweise keinen Standort vom Standortinformationsdienst abrufen oder keine Verbindung mit dem Dienstanbieter für Notrufdienste herstellen. Skype for Business bietet mehrere Strategien für die Behandlung von VoIP-Resilienz in Zweigstellen, einschließlich: Ausfallsicherheit von Datennetzwerken, Bereitstellen eines SIP-Trunks an jeder Zweigstelle oder Senden von Notrufen an das lokale Gateway bei Ausfällen. Ausführliche Informationen finden Sie unter [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).

 **Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**

 Die automatische Standorterfassung ist nur für Clients verfügbar, die sich im Netzwerk der Organisation befinden. Daher muss Ihre Organisation entscheiden, ob E9-1-1-Anrufe von Skype for Business Clients unterstützt werden, die außerhalb des Standorts getätigt werden. Können Benutzer beispielsweise Notrufe tätigen, wenn sie von zu Hause aus oder von einer Kundenwebsite aus arbeiten? Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client so konfiguriert werden, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird. Da diese vom Benutzer bereitgestellten Standorte jedoch nicht anhand des Master Street Address Guide (MSAG) vorab überprüft werden können, muss der Verteiler des Notrufdienstes die Gültigkeit des Standorts mit dem Anrufer bestätigen, bevor der Anruf an die Rettungsleitstelle (Public Safety Answering Point, PSAP) weiterleitet.

> [!NOTE]
> Skype for Business Clients von Benutzern, die über VPN eine Verbindung mit dem Netzwerk Ihrer Organisation herstellen, können interne IP-Adressinformationen abrufen. Da diese Adressen jedoch nicht zum Identifizieren des tatsächlichen Standorts des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze vom Standortinformationsdienst ausgeschlossen werden.

 **Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**

 Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter für die Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten VoIP-Richtlinien zu, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird.