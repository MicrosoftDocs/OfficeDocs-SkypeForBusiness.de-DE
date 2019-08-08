---
title: Planen der Migration von Skype for Business Server und Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: In diesem Thema wird erläutert, was Sie berücksichtigen müssen, wenn Sie Ihre vorhandenen Skype for Business Server oder Exchange Server-Bereitstellungen auf die neueste Version oder auf Skype for Business Online oder Exchange Online migrieren möchten.
ms.openlocfilehash: 864a777c1fcb483df7f3779e9b105c1af551748e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237470"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planen der Migration von Skype for Business Server und Exchange Server

In diesem Thema wird erläutert, was Sie berücksichtigen müssen, wenn Sie Ihre vorhandenen Skype for Business Server oder Exchange Server-Bereitstellungen auf die neueste Version oder auf Skype for Business Online oder Exchange Online migrieren möchten. Was Sie migrieren können und wann, hängt stark davon ab, was Sie in Ihrer Organisation bereits eingerichtet haben. Einige Funktionen, beispielsweise die automatische Telefonzentrale, sind nicht verfügbar (allgemeine Verfügbarkeit), werden aber später in 2018.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Funktionsänderungen in Exchange 2019 und Skype for Business Server 2019

Mit Exchange 2019 und Skype for Business Server 2019 werden einige Änderungen an den von uns unterstützten Features vorgenommen.

### <a name="unified-messaging-support-in-exchange-2019"></a>Unified Messaging-Unterstützung in Exchange 2019

Unified Messaging (um) wurde in Exchange 2019 veraltet. Dies bedeutet, dass Exchange 2019 nicht mehr die folgenden Features bietet:

- Voicemail
- Automatische Telefonzentrale

Wenn Sie die um-Rolle in Exchange 2013 oder den um-Dienst in Exchange 2016 bereitgestellt haben und ein Upgrade auf Exchange 2019 durchführen möchten, müssen Sie Ihre Voicemail in Office 365 in den Microsoft Cloud Voicemail-Dienst migrieren. Wenn Sie Ihre Voicemail in Cloud Voicemail migrieren möchten, sehen Sie sich die [Exchange 2013/Exchange 2016 und Skype for Business 2015 zu Exchange 2019 und Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) Abschnitt unten an.
> [!IMPORTANT]
> Wenn Benutzer auf Ihren Exchange 2013-oder Exchange 2016-Servern um-aktivierte Postfächer haben, verschieben Sie Sie nicht vor dem Upgrade Ihrer Skype for Business-Server auf Skype for Business Server 2019 und verschieben Sie die Benutzer zu Exchange 2019, um einen Ausfall von Sprachnachrichten zu vermeiden.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>PBX-Unterstützung in Exchange 2019 und Skype for Business Server 2019

Cloud-Voicemail bietet keine Sprachnachrichten Funktion für PBX-Anlagen (Private Branch eXchanges). Wenn Sie Exchange Server Unified Messaging für Nebenstellenanlagen verwenden und ein Upgrade auf Exchange Server 2019 durchführen möchten, müssen Sie eine der drei Optionen im Blogbeitrag [Neues Datum für die Einstellung der Unterstützung für Session Border Controller in Exchange auflisten. Online Unified Messaging](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) im [Blog des Exchange-Teams](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online um-Support in Skype for Business Server 2019

Mit Skype for Business Server 2019 werden wir von Exchange Online um in Cloud-Voicemail umziehen. Wenn ein Benutzer auf einen Skype for Business 2019-Server verschoben wird, startet er automatisch Cloud-Voicemail, wenn er für die gehostete Voicemail konfiguriert ist. Wenn Sie derzeit Exchange Online um verwenden, müssen Sie nichts anderes tun, als den Benutzer zu Skype for Business Server 2019 zu bewegen, um Cloud-Voicemail zu verwenden. Es gibt jedoch einige Änderungen an der Funktionalität, die Sie beachten müssen:

- Die automatische Telefonzentrale (die Ersetzung für die automatische Telefonzentrale in Exchange Online um) ist bei GA nicht verfügbar, wird jedoch später in 2018 verfügbar sein.
- Die Einstellungen für Benutzer Voicemail in Outlook im Internet gelten nicht für Cloud-Voicemail.

## <a name="on-premises-um-migration-scenarios"></a>Lokale um-Migrationsszenarien

Wir unterstützen die folgenden Szenarien, mit denen Sie Benutzer sowohl zu Exchange 2019 als auch zur Cloud-Voicemail migrieren können. Später in 2018 werden weitere Szenarien unterstützt, mit denen Sie von weiteren Versionen von Exchange und Skype for Business Server migrieren können. Außerdem stellen wir zusätzliche Features wie die automatische Telefonzentrale für die Organisation bereit.

- Exchange 2013/Exchange 2016 und Skype for Business Server 2015 auf Exchange 2019 und Skype for Business Server 2019
- Skype for Business Server 2015 zu Skype for Business Server 2019 mit Exchange 2013/Exchange 2016

Die folgenden Szenarien erfordern, dass keine Nebenstellenanlage oder SBC-Konfigurationen als Teil Ihrer aktuellen Bereitstellung vorhanden sind und davon ausgehen, dass Sie um auf Ihren lokalen Exchange-Servern konfiguriert haben. Bei jeder dieser Lösungen wird auch davon ausgegangen, dass Sie sich für die Konfiguration einer hybridbereitstellung zwischen Ihren lokalen Skype for Business Servern und Office 365 entschieden haben. Weitere Informationen zu Skype for Business hybridbereitstellungen finden Sie unter [Plan Hybrid Connectivity](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 und Skype for Business 2015 auf Exchange 2019 und Skype for Business 2019

In diesem Szenario möchten Sie die vorhandenen Exchange 2013, Exchange 2016 und Skype for Business 2015 Server zu Exchange 2019 und Skype for Business 2019 migrieren.

Wie weiter oben in diesem Thema erwähnt, enthält Exchange 2019 den um-Dienst nicht mehr. Dies bedeutet, dass Sie für alle Postfächer, die Sie zu Exchange 2019 verschieben möchten, die Cloud-Voicemail verwenden müssen, um die vom um-Dienst bereitgestellte Funktionalität zu ersetzen. Wenn Sie Skype for Business Server 2019 und eine hybridbereitstellung zwischen IT und Office 365 einrichten, ersetzt Cloud Voicemail diese Exchange um Voicemail-Dienste.

Die Reihenfolge, in der Sie Benutzer zu Exchange 2019 und Skype for Business Server 2019 migrieren, ist wichtig, um sicherzustellen, dass die Voicemailfunktionen für alle Benutzer verfügbar bleiben. Bei der Verarbeitung von Voicemail wird auch festgelegt, wo sich die Exchange-und Skype for Business-Postfächer und-Benutzer befinden. Sehen Sie sich die folgende Tabelle an, um herauszufinden, welche Kombinationen von Exchange und Skype for Business Server unterstützt werden und wo Voicemail verarbeitet wird.

| Das Postfach befindet sich unter:            | Benutzer, der sich auf Skype for Business Server 2015 befindet | Benutzer befindet sich auf Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | Nicht unterstützt                           | Cloud-Voicemail                          |

Beachten Sie Folgendes, bevor Sie mit der Migration zu Skype for Business Server 2019 und Exchange 2019 beginnen:

- Cloud Voicemail unterstützt keine organisatorische automatische Telefonzentrale bei GA. Wenn Sie möchten, dass Postfächer in Cloud-Voicemail verschoben werden, um weiterhin über die automatische Telefonzentrale verfügbar zu sein, müssen Sie mindestens einen Exchange 2013-oder Exchange 2016-Server mit der um-Rolle oder dem Dienst verfügbar halten.
- Sie müssen mindestens einen Skype for Business 2019-Server einrichten **und** Benutzer auf diesen Server verschieben, bevor Sie Ihre Postfächer zu Exchange 2019 verschieben. Andernfalls können die Postfächer keine Voicemail-Nachrichten empfangen.
- Anrufe, die an Voicemail gesendet werden, werden an die Cloud-Voicemail übertragen, wo Sie aufgezeichnet werden. Nachdem der Anruf beendet wurde, wird die Voicemail-Nachricht an das Postfach des Empfängers auf dem lokalen Exchange 2019-Server gesendet. Sie müssen diesen Sprachdatenverkehr berücksichtigen, wenn Sie feststellen, ob Ihre Internet Verbindung ausreicht, um Cloud-Voicemail zu unterstützen.

Hier finden Sie die allgemeinen Schritte zum Abschließen dieser Migration.

1. Installieren und konfigurieren Sie Skype for Business Server 2019 auf einem neuen Server.
2. Aktualisieren Sie Ihre Hybrid Bereitstellungskonfiguration so, dass Sie den neuen Skype for Business 2019-Server enthält.
3. Installieren und konfigurieren Sie Exchange Server 2019 auf einem neuen Server.
4. Migrieren Sie Benutzer von Ihrem Skype for Business 2015 Server auf Ihren Skype for Business 2019-Server.
5. Legen Sie die Richtlinie für gehostete Voicemail für jeden Benutzer, der auf Skype for Business Server 2019 verschoben wurde, für die Verwendung von Cloud Voicemail fest.
6. Verschieben Sie Postfächer von Ihrem Exchange 2013 oder Exchange 2016-Server auf Ihren Exchange 2019-Server.
7. Außerbetriebnahme Ihrer Skype for Business 2015 Server, nachdem der letzte Benutzer von Ihnen verschoben wurde.
8. Außer Betrieb Ihrer Exchange 2013-oder Exchange 2016-Server, nachdem das letzte Postfach von Ihnen verschoben wurde.

    > [!IMPORTANT]
    > Wenn Sie eine automatische Telefonzentrale verwenden, halten Sie mindestens eine Exchange 2013 oder Exchange 2016, die aktiv ist und verfügbar ist.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 zu Skype for Business Server 2019 mit Exchange 2013/Exchange 2016

In diesem Szenario möchten Sie den vorhandenen Skype for Business 2015 Server auf Skype for Business Server 2019 migrieren, jedoch auf Exchange 2013 oder Exchange 2016 verbleiben.

Wenn Skype for Business Server 2015 und Skype for Business Server 2019 in derselben Organisation vorhanden sind, arbeiten Sie nahtlos mit Exchange um und Cloud-Voicemail zusammen, um sicherzustellen, dass Voicemail ordnungsgemäß an Exchange-Postfächerüber mittelt wird. Unabhängig davon, ob Exchange um-oder Cloud-Voicemail die Voicemail verarbeitet, hängt davon ab, ob sich der Benutzer in Skype for Business Server 2015 oder Skype for Business Server 2019 befindet:

- Wenn sich ein Benutzer auf Skype for Business Server 2015 befindet, wird die Voicemail-Nachricht von Exchange um verarbeitet.
- Wenn sich ein Benutzer in Skype for Business Server 2019 befindet, verarbeitet Cloud Voicemail die Voicemail-Nachricht.

Unabhängig davon, ob Exchange um-oder Cloud-Voicemail die Voicemail-Nachricht verarbeitet, wird die Nachricht im Exchange-Postfach des Benutzers gespeichert.

Bevor Sie mit der Migration zu Skype for Business Server 2019 beginnen, sollten Sie Folgendes berücksichtigen:

- Cloud Voicemail unterstützt keine organisatorische automatische Telefonzentrale bei GA. Wenn Sie möchten, dass Postfächer in Cloud-Voicemail verschoben werden, um weiterhin über die automatische Telefonzentrale verfügbar zu sein, müssen Sie mindestens einen Exchange 2013-oder Exchange 2016-Server mit der um-Rolle oder dem Dienst verfügbar halten.
- Anrufe, die an Voicemail gesendet werden, werden an die Cloud-Voicemail übertragen, wo Sie aufgezeichnet werden. Nachdem der Anruf beendet wurde, wird die Voicemail-Nachricht an das Postfach des Empfängers auf dem lokalen Exchange-Server gesendet. Sie müssen diesen Sprachdatenverkehr berücksichtigen, wenn Sie feststellen, ob Ihre Internet Verbindung ausreicht, um Cloud-Voicemail zu unterstützen.

Hier finden Sie die allgemeinen Schritte zum Abschließen dieser Migration.

1. Installieren und konfigurieren Sie Skype for Business Server 2019 auf einem neuen Server.
2. Aktualisieren Sie Ihre Hybrid Bereitstellungskonfiguration so, dass Sie den neuen Skype for Business 2019-Server enthält.
3. Migrieren Sie Benutzer von Ihrem Skype for Business 2015 Server auf Ihren Skype for Business 2019-Server.
4. Legen Sie die Richtlinie für gehostete Voicemail für jeden Benutzer, der auf Skype for Business Server 2019 verschoben wurde, für die Verwendung von Cloud Voicemail fest.
5. Außerbetriebnahme Ihrer Skype for Business 2015 Server, nachdem der letzte Benutzer von Ihnen verschoben wurde.

    > [!IMPORTANT]
    > Wenn Sie eine automatische Telefonzentrale verwenden, halten Sie mindestens eine Exchange 2013 oder Exchange 2016, die aktiv ist und verfügbar ist.
