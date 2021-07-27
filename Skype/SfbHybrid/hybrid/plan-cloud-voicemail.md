---
title: Planen Cloud-Voicemail Diensts für lokale Benutzer| PBX Skype for Business Server 2019
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
description: In diesem Artikel werden Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung des Microsoft Cloud-Voicemail-Diensts beschrieben. Informationen zum Konfigurieren von Cloud-Voicemail finden Sie unter "Konfigurieren von Cloud-Voicemail".
ms.openlocfilehash: cfde9867bcdd4c2b7492f8b50df782a5ca6fe34b
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509836"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planen Cloud-Voicemail Diensts für lokale Benutzer

## <a name="overview"></a>Übersicht

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Artikel werden Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung des Microsoft Cloud-Voicemail-Diensts für Ihre lokalen Benutzer beschrieben. Informationen zum Konfigurieren von Cloud-Voicemail finden Sie unter [Konfigurieren Cloud-Voicemail Diensts.](configure-cloud-voicemail.md)

Cloud-Voicemail ersetzt Exchange Unified Messaging (UM) bei der Bereitstellung von Voice Messaging-Funktionen für Skype for Business 2019-VoIP-Benutzer, die über Postfächer Exchange Server 2019 oder Exchange Online verfügen. Cloud-Voicemail bietet die folgenden Vorteile für Ihre lokalen und Onlinebenutzer:

- Voicemail-Antwort- und -Hinterlegungsfunktionen mit erweiterter Sprachtranskription

- Zugriff auf Voicemail im Exchange Postfach des Benutzers mithilfe der Skype for Business Online- oder Outlook-Clients

- Die Möglichkeit, die Microsoft 365 Admin Center zum Verwalten von Voicemailoptionen zu verwenden

- Unterstützung für Exchange Postfächer lokal oder in der Cloud

- Nutzen vorhandener Benutzergrüße von Exchange Online Unified Messaging

> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nach dem Benutzer nicht mehr über den Skype for Business Online-Client auf Voicemail in ihrem Exchange Postfach zugreifen können.

Weitere Informationen zum Featurevergleich finden Sie unter [Plan for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)

Skype for Business Server 2019 verwendet weiterhin Exchange UM für Benutzer, deren Postfächer sich in früheren Versionen von Exchange Server befinden (2013, 2016).  Das Verständnis, welche Voicemaillösung basierend auf der Exchange Server und Skype for Business Server Version verwendet wird, ist ein wichtiger Bestandteil der Planung für die Migration zu Skype for Business Server 2019 oder Exchange Server 2019. Weitere Informationen zur Migration und Interoperabilität finden Sie unter [Plan for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)

Mit Cloud-Voicemail werden Ihre Verwaltungsaufgaben aus folgenden Gründen erheblich vereinfacht:

- Es ist nicht erforderlich, die Exchange UM-Rolle zu konfigurieren.
- Die Einrichtungsaufgaben für Cloud-Voicemail sind einfacher.
- Updates für voicemail-Funktionen werden direkt in der Cloud bereitgestellt, sodass Ihre Benutzer immer Zugriff auf die neuesten Features und Updates haben, die weniger von kumulativen Updates (Kumulierte Updates, CUs) abhängig sind.
- Sie verfügen über den gleichen Satz von Steuerelementen für lokale und Online-Exchange Postfächer. Weitere Informationen zu diesen Steuerelementen finden Sie unter [Einrichten Telefonsystem Voicemail.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

Das folgende Diagramm zeigt Cloud-Voicemail in einer Hybridbereitstellung:

![SfB Cloud-Voicemail](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Nicht beantwortete Anrufe werden wie folgt behandelt:  

1. Für Benutzer, die in Skype for Business 2019 lokal verwaltet werden, werden nicht beantwortete Anrufe vom lokalen Skype for Business Server an den Online-Cloud-Voicemail Dienst gesendet.
2. Der Dienst verarbeitet die Voicemail, einschließlich Transkription.
3. Der Dienst übergibt dann die Voicemail im Exchange Postfach des Benutzers, unabhängig davon, ob das Postfach lokal oder online ist.  
4. Benutzer können entweder über ihren Skype for Business- oder Outlook-Client auf ihre Voicemail zugreifen.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype for Business Server in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Wenn Sie bereits Exchange UM online verwenden und auf Skype for Business 2019 aktualisieren, müssen Sie Ihre gehostete Voicemailrichtlinie ändern und überprüfen, ob Ihre Hostinganbieter korrekt festgelegt sind. Weitere Informationen finden Sie unter [Konfigurieren Cloud-Voicemail Diensts.](configure-cloud-voicemail.md)

- Wenn Sie Exchange um lokal verwenden oder eine Kombination aus Benutzern haben, die Exchange UM online und lokal verwenden, müssen Sie sowohl Ihre gehostete Voicemailrichtlinie als auch den Hostinganbieter ändern.  Weitere Informationen finden Sie unter [Konfigurieren Cloud-Voicemail Diensts.](configure-cloud-voicemail.md)

- Führen Sie für eine neue Konfiguration von Cloud-Voicemail die unter [Konfigurieren Cloud-Voicemail Dienst](configure-cloud-voicemail.md)beschriebenen Schritte aus.

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem Microsoft Cloud-Voicemail Dienst hergestellt wird:

- Hybridkonnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und Cloud-Voicemail für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass die Hybridkonnektivität zwischen Ihrer lokalen und Onlineumgebung eingerichtet ist. Dies wird manchmal als Konfiguration für geteilte Domänen bezeichnet.

   Weitere Informationen finden Sie unter Planen der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md) und Konfigurieren der [Hybridkonnektivität zwischen Skype for Business Server und Office 365.](configure-hybrid-connectivity.md)

- Lokale Benutzer müssen für Enterprise-VoIP und gehostete Voicemail in Skype for Business Server aktiviert sein.

- Eine URL und AutoErmittlung für externe Exchange Webdienste (External Exchange Web Services, EWS) müssen eingerichtet werden, oder einige Cloud-Voicemail Features sind eingeschränkt.

- Wenn Sie über einen lokalen Exchange Server verfügen, richten Sie Cloud-Voicemail mithilfe der Schritte unter [Einrichten von Cloud-Voicemail für Exchange Server Postfachbenutzer](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)ein.

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie planen, Skype for Business Server 2019 und/oder Exchange Server 2019 bereitzustellen, müssen Sie Ihre Migration sorgfältig planen, um sicherzustellen, dass der Dienst für Voice messaging fortgesetzt wird. Denken Sie dabei an Folgendes:

- Exchange Server 2019 bietet keine Exchange UM-Funktionalität mehr
- Skype for Business Server 2019 wird nicht mehr in Exchange Online UM integriert

Versionsinteroperabilität und unterstützte Topologien für Cloud-Voicemail sind in der folgenden Tabelle aufgeführt, in der die Skype for Business Server Versionen, in denen der Benutzer verwaltet werden kann, mit der möglichen Version verglichen werden, die sein Exchange Postfach bereitstellt. Sie müssen Cloud-Voicemail verwenden, wenn Sie Skype for Business 2019 mit Exchange Online oder Exchange Server 2019 verwenden möchten.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | Cloud-Voicemail | Cloud-Voicemail |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | Nicht unterstützt | Cloud-Voicemail |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | Nicht unterstützt | Cloud-Voicemail |

Microsoft empfiehlt die folgenden Migrationspfade:

- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen, können Sie Exchange UM in Exchange Server 2013 oder 2016 verwenden, aber Sie müssen ein Upgrade auf Cloud-Voicemail durchführen, wenn Sie Exchange Server 2019 verwenden.
- Wenn Sie ein Upgrade auf Exchange Server 2019 durchführen und frühere Versionen von Exchange Server UM für Skype for Business Server Voice messaging verwenden, empfiehlt Microsoft, vor dem Postfachupgrade auf Skype for Business Server 2019 zu aktualisieren.  Andernfalls geht die Sprachnachrichtenfunktion verloren.
- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen und Skype for Business Server 2015 für Voicemail mit Exchange Online UM konfiguriert haben, wird die Voicemail der Benutzer automatisch von Exchange Online UM zu Cloud-Voicemail migriert, wenn ihr Konto auf Skype for Business Server 2019 verschoben wird. 

Weitere Informationen zum Planen Der Migration finden Sie unter [Planen der Skype for Business Server und Exchange Server Migration.](plan-um-migration.md)