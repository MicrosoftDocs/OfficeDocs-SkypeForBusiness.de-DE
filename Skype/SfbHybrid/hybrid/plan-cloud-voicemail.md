---
title: Planen des Cloud-Voicemail-Diensts für lokale Benutzer | Nebenstellenanlage Skype for Business Server 2019
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
description: In diesem Artikel werden die Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung des Microsoft Cloud Voicemail-Diensts beschrieben. Informationen zum Konfigurieren von Cloud-Voicemail finden Sie unter Configuring Cloud Voicemail.
ms.openlocfilehash: 30a4983c79f4a7cddd274c272b5a094c17653bbb
ms.sourcegitcommit: 7c08d88dcaa85e34e93131bb9a5a64597c6d8155
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210631"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planen des Cloud-Voicemail-Diensts für lokale Benutzer

## <a name="overview"></a>Übersicht

In diesem Artikel werden die Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung des Microsoft Cloud Voicemail-Diensts für Ihre lokalen Benutzer beschrieben. Informationen zum Konfigurieren von Cloud-Voicemail finden Sie unter [configure Cloud Voicemail Service](configure-cloud-voicemail.md).

Cloud-Voicemail übernimmt Exchange Unified Messaging (um) bei der Bereitstellung von VoIP-Funktionen für Skype for Business 2019-VoIP-Benutzer mit Postfächern in Exchange Server 2019 oder Exchange Online. Cloud Voicemail bietet die folgenden Vorteile sowohl für lokale als auch für Online Benutzer:

- Voicemail-Anrufbeantworter-und-Einzahlungs Funktionen mit erweiterter Sprachtranskription

- Zugriff auf Voicemail im Exchange-Postfach des Benutzers mithilfe der Skype for Business Online-oder Outlook-Clients

- Die Möglichkeit, das Office 365 webbasierte Portal zum Verwalten von Voicemail-Optionen zu verwenden

- Unterstützung für Exchange-Postfächer lokal oder in der Cloud

- Nutzung vorhandener Begrüßungen von Benutzern aus Exchange Online Unified Messaging

Weitere Informationen zum Funktionsvergleich finden Sie unter [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Skype for Business Server 2019 verwendet weiterhin Exchange um für Benutzer, deren Postfächer sich in früheren Versionen von Exchange Server (2013, 2016) befinden.  Das Verständnis, welche Voicemaillösung basierend auf der Exchange Server und Skype for Business Server Version verwendet wird, ist ein wichtiger Bestandteil der Planung der Migration zu Skype for Business Server 2019 oder Exchange Server 2019. Weitere Informationen zur Migration und Interoperabilität finden Sie unter [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Bei Cloud Voicemail werden Ihre Verwaltungsaufgaben wesentlich vereinfacht, da:

- Es ist nicht erforderlich, die Exchange um Rolle zu konfigurieren.
- Die Setupaufgaben für Cloud-Voicemail sind einfacher.
- Updates für Voicemailfunktionen werden direkt in der Cloud bereitgestellt, sodass Ihre Benutzer immer Zugriff auf die neuesten Funktionen und Updates mit geringerer Abhängigkeit von kumulativen Updates (CUS) haben.
- Sie verfügen über dieselben Steuerelemente für lokale und Online-Exchange-Postfächer. Weitere Informationen zu diesen Steuerelementen finden Sie unter [Einrichten von Voicemail für Telefonsysteme](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

Das folgende Diagramm zeigt Cloud-Voicemail in einer hybridbereitstellung:

![SFB Cloud Voicemail](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Nicht beantwortete Anrufe werden wie folgt behandelt:  

1. Für Benutzer, die in Skype for Business 2019 lokal verwaltet werden, werden unbeantwortete Anrufe vom lokalen Skype for Business Server an den Online Cloud-Voicemaildienst gesendet.
2. Der Dienst verarbeitet die Voicemail, einschließlich Transkription.
3. Der Dienst legt dann die Voicemail im Exchange-Postfach des Benutzers ab, unabhängig davon, ob das Postfach lokal oder Online ist.  
4. Benutzer können über Ihre Skype for Business oder den Outlook-Client auf Ihre Voicemail zugreifen.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird vorausgesetzt, dass Sie bereits Skype for Business Server in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Wenn Sie bereits Exchange um Online verwenden und ein Upgrade auf Skype for Business 2019 durchführen, müssen Sie die Richtlinie für gehostete Voicemail ändern und überprüfen, ob Ihre Hostinganbieter ordnungsgemäß festgelegt sind. Weitere Informationen finden Sie unter [configure Cloud Voicemail Service](configure-cloud-voicemail.md).

- Wenn Sie Exchange um lokal verwenden oder eine Mischung aus Benutzern mit Exchange um Online und lokal verwenden, müssen Sie sowohl die Richtlinie für gehostete Voicemail als auch den Hostinganbieter ändern.  Weitere Informationen finden Sie unter [configure Cloud Voicemail Service](configure-cloud-voicemail.md).

- Für eine neue Konfiguration von Cloud-Voicemail führen Sie die unter [configure Cloud Voicemail Service](configure-cloud-voicemail.md)beschriebenen Schritte aus.

Zusätzlich zu den oben aufgeführten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem Microsoft Cloud Voicemail-Dienst hergestellt wird:

- Hybrid Konnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und Cloud-Voicemail für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Sie eine hybride Konnektivität zwischen Ihren lokalen und Online-Umgebungen eingerichtet haben. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](plan-hybrid-connectivity.md) und [Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](configure-hybrid-connectivity.md).

- Lokale Benutzer müssen für Enterprise-VoIP und für gehostete Voicemail in Skype for Business Server aktiviert sein.

- Eine externe Exchange-Webdienste-URL und AutoErmittlung muss eingerichtet sein, oder einige Cloud Voicemail-Funktionen sind limitiert.

- Wenn Sie nur über eine lokale Bereitstellung verfügen&#x2014;das heißt, dass nur Exchange-und Skype for Business lokale Server&#x2014;aber Cloud-Voicemail nutzen möchten, benötigen Sie eine Telefon System Lizenz.

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie Skype for Business Server 2019 und/oder Exchange Server 2019 bereitstellen möchten, müssen Sie die Migration sorgfältig planen, um die Fortsetzung des Diensts für Sprachnachrichten sicherzustellen. Denken Sie dabei an Folgendes:

- Exchange Server 2019 bietet keine Exchange um Funktionalität mehr
- Skype for Business Server 2019 nicht mehr in Exchange Online um integriert

Versions Interoperabilität und unterstützte Topologien für Cloud-Voicemail sind in der folgenden Tabelle aufgeführt, in der die Skype for Business Server Versionen, auf denen der Benutzer möglicherweise verwaltet wird, mit der möglichen Version verglichen werden, die das Exchange-Postfach bereitstellt. Sie müssen Cloud Voicemail verwenden, wenn Sie Skype for Business 2019 mit Exchange Online oder Exchange Server 2019 verwenden möchten.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server um | Exchange Server um | Cloudvoicemail | Cloudvoicemail |
| Skype for Business Server 2015 | Exchange Server um | Exchange Server um | Cloudvoicemail | Cloudvoicemail |
| Lync Server 2013 <br>  | Exchange Server um | Exchange Server um | Nicht unterstützt | Cloudvoicemail |

Microsoft empfiehlt die folgenden Migrationspfade:

- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen, können Sie Exchange um in Exchange Server 2013 oder 2016 verwenden, aber Sie müssen ein Upgrade auf Cloud Voicemail durchführen, wenn Sie Exchange Server 2019 verwenden.
- Wenn Sie ein Upgrade auf Exchange Server 2019 durchführen und frühere Versionen von Exchange Server um für Skype for Business Server Sprachnachrichten verwenden, empfiehlt Microsoft, ein Upgrade auf Skype for Business Server 2019 vor dem Post Fach Upgrade durchführen.  Andernfalls geht die Sprachnachrichten Funktion verloren.
- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen und Skype for Business Server 2015 für Voicemail mit Exchange Online Unified Messaging konfiguriert haben, wird die Voicemail der Benutzer automatisch von Exchange Online um in Cloud Voicemail migriert, wenn Ihr Konto auf Skype for Business Server 2019 verschoben wird. 

Weitere Informationen zum Planen der Migration finden Sie unter [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).
