---
title: Planen des Cloud-Voicemaildiensts für lokale Benutzer| Nebenstellenanlage Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: In diesem Artikel werden Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung des Microsoft Cloud Voicemail-Diensts beschrieben. Informationen zum Konfigurieren von Cloud Voicemail finden Sie unter Configuring Cloud Voicemail.
ms.openlocfilehash: 4ae274f33d2b7d52c486cd9031d01bc3a532a6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110281"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planen des Cloud-Voicemaildiensts für lokale Benutzer

## <a name="overview"></a>Übersicht

In diesem Artikel werden Die Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung des Microsoft Cloud Voicemail-Diensts für Ihre lokalen Benutzer beschrieben. Informationen zum Konfigurieren von Cloud Voicemail finden Sie unter [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

Cloud Voicemail übernimmt die Stelle von Exchange Unified Messaging (UM) bei der Bereitstellung von Voicenachrichtenfunktionen für Skype for Business 2019-Sprachbenutzer, die über Postfächer in Exchange Server 2019 oder Exchange Online verfügen. Cloud Voicemail bietet die folgenden Vorteile für Lokale und Onlinebenutzer:

- Voicemailbeantwortungs- und -hinterlegungsfunktionen mit erweiterter Sprach transkription

- Zugriff auf Voicemail im Exchange-Postfach des Benutzers mithilfe der Skype for Business Online- oder Outlook-Clients

- Die Möglichkeit, das Microsoft 365 Admin Center zum Verwalten von Voicemailoptionen zu verwenden

- Unterstützung für Exchange-Postfächer lokal oder in der Cloud

- Nutzen vorhandener Benutzergrüße aus Exchange Online Unified Messaging

> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem Benutzer nicht mehr über den Skype for Business Online-Client auf Voicemail in ihrem Exchange-Postfach zugreifen können.

Weitere Informationen zum Featurevergleich finden Sie unter [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Skype for Business Server 2019 verwendet weiterhin Exchange UM für Benutzer, deren Postfächer in früheren Versionen von Exchange Server (2013, 2016) vorhanden sind.  Zu verstehen, welche Voicemaillösung basierend auf der Exchange Server- und Skype for Business Server-Version verwendet wird, ist ein wichtiger Bestandteil der Planung der Migration zu Skype for Business Server 2019 oder Exchange Server 2019. Weitere Informationen zur Migration und Interoperabilität finden Sie unter [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Mit Cloud Voicemail werden Ihre Verwaltungsaufgaben erheblich vereinfacht, da:

- Die Exchange -UM-Rolle muss nicht konfiguriert werden.
- Die Setupaufgaben für Cloud Voicemail sind einfacher.
- Updates für die Voicemailfunktionalität werden direkt in der Cloud zugestellt, sodass Ihre Benutzer immer Zugriff auf die neuesten Features und Updates haben, die weniger von kumulativen Updates (Cumulative Updates, CUs) abhängig sind.
- Sie verfügen über den gleichen Satz von Steuerelementen für lokale und Online-Exchange-Postfächer. Weitere Informationen zu diesen Steuerelementen finden Sie unter [Einrichten der Voicemail des Telefonsystems.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

Das folgende Diagramm zeigt Cloud Voicemail in einer Hybridbereitstellung:

![SfB Cloud Voicemail](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Nicht beantwortete Anrufe werden wie folgt behandelt:  

1. Für Benutzer, die in Skype for Business 2019 lokal zu Hause sind, werden nicht beantwortete Anrufe vom lokalen Skype for Business Server an den Online-Cloud-Voicemaildienst gesendet.
2. Der Dienst verarbeitet die Voicemail, einschließlich Transkription.
3. Der Dienst hinterlegt dann die Voicemail im Exchange-Postfach des Benutzers, unabhängig davon, ob das Postfach lokal oder online ist.  
4. Benutzer können über ihren Skype for Business- oder Outlook-Client auf ihre Voicemail zugreifen.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Skype for Business Server bereits in einer unterstützten Topologie bereitgestellt ist.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Wenn Sie Exchange UM online bereits verwenden und ein Upgrade auf Skype for Business 2019 durchführen, müssen Sie Ihre gehostete Voicemailrichtlinie ändern und überprüfen, ob Ihre Hostinganbieter ordnungsgemäß festgelegt sind. Weitere Informationen finden Sie unter [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Wenn Sie Exchange UM lokal verwenden oder über eine Mischung aus Benutzern verfügen, die Exchange UM online und lokal verwenden, müssen Sie sowohl Ihre gehostete Voicemailrichtlinie als auch den Hostinganbieter ändern.  Weitere Informationen finden Sie unter [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Führen Sie für eine neue Konfiguration von Cloud Voicemail die unter [Configure Cloud Voicemail service beschriebenen Schritte aus.](configure-cloud-voicemail.md)

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen für die Verbindung mit dem Microsoft Cloud Voicemaildienst konfiguriert werden:

- Hybridkonnektivität. Wenn Sie Skype for Business Server bereits bereitgestellt haben und Cloud Voicemail für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Hybridkonnektivität zwischen Ihren lokalen und Onlineumgebungen eingerichtet ist. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) und [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).

- Lokale Benutzer müssen für die Enterprise-VoIP und gehostete Voicemail in Skype for Business Server aktiviert sein.

- Eine EWS-URL (External Exchange Web Services) und die AutoErmittlung müssen eingerichtet werden, oder einige Cloud Voicemailfeatures sind eingeschränkt.

- Wenn Sie über einen lokalen Exchange-Server verfügen, richten Sie Cloud voicemail mithilfe der Schritte unter Einrichten von [Cloud voicemail für](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)Postfachbenutzer Exchange Server ein.

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie Planen der Bereitstellung von Skype for Business Server 2019 und/oder Exchange Server 2019, müssen Sie Ihre Migration sorgfältig planen, um den weiteren Dienst für Voice messaging sicherzustellen. Denken Sie dabei an Folgendes:

- Exchange Server 2019 bietet keine Exchange UM-Funktionen mehr
- Skype for Business Server 2019 ist nicht mehr in Exchange Online UM integriert

Versionsinteroperabilität und unterstützte Topologien für Cloud Voicemail sind in der folgenden Tabelle aufgeführt, in der die Skype for Business Server-Versionen verglichen werden, in denen der Benutzer möglicherweise mit der möglichen Version, die sein Exchange-Postfach zur Verfügung stellt, unterstützt wird. Sie müssen Cloud Voicemail verwenden, wenn Sie Skype for Business 2019 mit Exchange Online oder Exchange Server 2019 verwenden möchten.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | Cloud-Voicemail | Cloud-Voicemail |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | Nicht unterstützt | Cloud-Voicemail |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | Nicht unterstützt | Cloud-Voicemail |

Microsoft empfiehlt die folgenden Migrationspfade:

- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen, können Sie Exchange UM in Exchange Server 2013 oder 2016 verwenden, Aber Sie müssen ein Upgrade auf Cloud Voicemail durchführen, wenn Sie Exchange Server 2019 verwenden.
- Wenn Sie ein Upgrade auf Exchange Server 2019 durchführen und frühere Versionen von Exchange Server UM für Skype for Business Server Voice Messaging verwenden, empfiehlt Microsoft, vor dem Postfachupgrade auf Skype for Business Server 2019 zu aktualisieren.  Andernfalls gehen die Sprachnachrichtenfunktionen verloren.
- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen und Skype for Business Server 2015 für Voicemail mit Exchange Online UM konfiguriert haben, wird die Voicemail der Benutzer automatisch von Exchange Online UM zu Cloud Voicemail migriert, wenn ihr Konto zu Skype for Business Server 2019 verschoben wird. 

Weitere Informationen zum Planen Ihrer Migration finden Sie unter [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).