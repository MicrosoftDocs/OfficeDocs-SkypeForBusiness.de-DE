---
title: Planen der Voicemail Cloud-Dienst
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Dieser Artikel beschreibt die Vorteile, Planungsaspekte, und Anforderungen für die Implementierung von Microsoft Cloud Voicemail-Dienst. Informationen zum Konfigurieren von Cloud-Voicemail finden Sie unter Konfigurieren von Cloud Voicemail.
ms.openlocfilehash: 8f7c2e394aa7d3f5a04961088202d1d9055eef9e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370634"
---
# <a name="plan-cloud-voicemail-service"></a>Planen der Voicemail Cloud-Dienst

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a>Übersicht 

Dieser Artikel beschreibt die Vorteile, Planungsaspekte, und Anforderungen für die Implementierung des Microsoft-Cloud-Voicemail-Diensts. Informationen zum Konfigurieren von Cloud-Voicemail finden Sie unter [Konfigurieren von Cloud-Voicemail-Dienst](configure-cloud-voicemail.md).

Cloud-Voicemail anstelle von Exchange Unified Messaging (UM) bei der Bereitstellung von Voice messaging-Funktionalität für Skype für Business 2019 VoIP-Benutzer, deren Postfächer auf Exchange Server 2019 oder Exchange Online. Cloud-Voicemail bietet die folgenden Vorteile für die lokalen und online-Benutzer:

- Voicemail beantworten und hinterlassen Funktionalität durch verbesserte Speech Lautschrift

- Zugriff auf Voicemail in Exchange-Postfach des Benutzers mithilfe der Skype für Business Online oder Outlook-clients 

- Die Möglichkeit, Web-basierte Office 365-Portal verwenden zum Verwalten von Voicemail-Optionen

- Unterstützung für Exchange-Postfächer lokal oder in der cloud

- Nutzen der vorhandenen Benutzer Ansage von Exchange Online Unified Messaging

Weitere Informationen zum Vergleich von Features finden Sie unter [Planen von Skype für Business Server und Exchange Server-Migration](plan-um-migration.md). 

Skype für Business Server 2019 verwendet weiterhin Exchange UM für Benutzer, deren Postfächer befinden sich auf früheren Versionen von Exchange Server (2013, 2016).  Verstehen, welche Voicemaillösung basierend auf dem Exchange-Server und Skype für Business Server verwendet wird-Version ist ein wichtiger Teil der Planung für die Migration zu entweder Skype für Business Server 2019 oder Exchange Server 2019. Weitere Informationen zu Migration und Interoperabilität finden Sie unter [Planen von Skype für Business Server und Exchange Server-Migration](plan-um-migration.md). 

Cloud-Voicemail werden Ihre Verwaltungsaufgaben erheblich, da vereinfacht:

- Es besteht keine Notwendigkeit zum Konfigurieren der Exchange UM-Rolle.
- Die Setupaufgaben für die Cloud Voicemail sind einfacher.
- Updates für Voicemail-Funktionen werden direkt in der Cloud übermittelt, damit Ihre Benutzer immer auf die neuesten Features und Updates mit weniger Abhängigkeit kumulativen Updates (Updates mit) zugreifen.
- Sie müssen dieselben Steuerelemente für lokale und Exchange online-Postfächern der. Weitere Informationen über diese Steuerelemente finden Sie unter [Einrichten von Voicemail Telefonsystem](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

Das folgende Diagramm zeigt die Cloud Voicemail in einer hybridbereitstellung:


![SfB Cloud-Voicemail](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Nicht beantwortete Anrufe werden folgendermaßen behandelt:  

1. Für Benutzer in Skype für Business 2019 lokal verwaltet werden, werden nicht beantwortete Anrufe an die Cloud Voicemail Onlinedienst von der lokalen Skype für Business Server gesendet. 
2. Der Dienst verarbeitet die Voicemail, einschließlich Lautschrift.
3. Der Dienst legt die Voicemail klicken Sie dann in der Exchange-Postfach des Benutzers, ob das Postfach befindet sich der lokale oder online.  
4. Benutzer können ihre Voicemail entweder ihre Skype für Business oder Outlook-Client zugreifen.

## <a name="requirements"></a>Anforderungen

Die folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype für Business Server in einer unterstützten Topologie bereitgestellt haben.  Standarddateispeicherort hängen des Szenarios:

- Wenn Sie bereits Exchange UM online verwenden und auf Skype für Business 2019 aktualisieren, müssen Sie zum Ändern der gehosteten voicemailrichtlinie, und stellen Sie sicher, dass Ihre Hostinganbieter richtig eingestellt sind. Weitere Informationen finden Sie unter [Konfigurieren von Cloud-Voicemail-Dienst](configure-cloud-voicemail.md).

- Wenn Sie Exchange UM lokal, oder Sie haben eine Kombination von Benutzern mithilfe von Exchange UM online und lokal, müssen Sie die gehostete voicemailrichtlinie und die Hostinganbieter ändern.  Weitere Informationen finden Sie unter [Konfigurieren von Cloud-Voicemail-Dienst](configure-cloud-voicemail.md).

- Befolgen Sie für eine neue Konfiguration von Cloud-Voicemail die Schritte in [Konfigurieren Cloud Voicemail-Dienst](configure-cloud-voicemail.md).

Neben den oben genannten Anforderungen die unter Anforderungen müssen zum Verbinden mit der Microsoft-Cloud-Voicemail-Dienst konfiguriert werden:

- Hybrid-Diensten. Wenn Sie bereits Skype für Business Server bereitgestellt, und Sie Cloud Voicemail für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Sie hybridkonnektivität zwischen Ihrer lokalen und online-Umgebung eingerichtet haben. Dies ist eine geteilte Domänenkonfiguration bezeichnet. 

   Weitere Informationen finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Office 365 planen](plan-hybrid-connectivity.md) und [Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Office 365](configure-hybrid-connectivity.md).

- In der lokalen Benutzer für Enterprise-VoIP und gehostete Voicemail in Skype für Business Server aktiviert werden müssen.

- Eine externe Exchange-Webdienste (EWS)-URL und AutoErmittlung eingerichtet werden oder einige Cloud Voicemail-Features eingeschränkt.

-  Wenn Sie eine lokale nur Bereitstellung –, die, nur Exchange und Skype für Unternehmen der lokale Server, aber Sie Voicemail Cloud nutzen möchten, benötigen Sie die ON PREM-Lizenz. 

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie beabsichtigen, Skype für Business Server 2019 und/oder 2019 der Exchange-Server bereitstellen, müssen Sie die Migration sorgfältig durch, um fortgesetzte Dienst für Voicemessaging sicherzustellen planen. Berücksichtigen Sie dabei Folgendes:

- Exchange Server 2019 bietet nicht mehr Exchange UM Funktionalität.
- Skype für Business Server 2019 integriert nicht mehr mit Exchange Online UM

Interoperabilität und unterstützten Topologien für die Cloud Voicemail sind in der folgenden Tabelle aufgeführt. Für die Preview-Version funktioniert Cloud Voicemail nur mit Skype für Business Server und Exchange Server 2019 oder Exchange Online.


|                               | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---------------------------    |:---------------------|:---------------------|:------------------|:---------------------- |
| Skype für Business Server 2019 | Exchange Server UM | Exchange Server UM | Cloud-Voicemail | Cloud-Voicemail
Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM |  | Cloud-Voicemail <br> Exchange Online UM * |
Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | | Cloud-Voicemail <br> Exchange Online UM * |

\*Bis veraltet.

Microsoft empfiehlt die folgenden Pfade für die Migration:

-  Wenn Sie auf Skype für Business Server 2019 durchführen, können Sie Exchange UM in Exchange Server 2013 oder 2016, aber Sie müssen an die Cloud Voicemail aktualisieren, wenn Sie Exchange Server 2019 verwenden.

- Wenn Sie auf Exchange Server 2019 aktualisieren und Sie frühere Versionen von Exchange Server UM für Skype für Voicemessaging Business Server verwenden, empfiehlt es sich, dass Sie vor dem Upgrade Postfach auf Skype für Business Server 2019 aktualisieren.  Anderenfalls verloren Voicemessaging-Funktionen. 


Weitere Informationen zur Planung der Migrations finden Sie unter [Planen von Skype für Business Server und Exchange Server-Migration](plan-um-migration.md).
