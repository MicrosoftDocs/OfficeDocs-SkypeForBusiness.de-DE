---
title: Planen der Migration von Skype for Business Server und Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: In diesem Thema wird erläutert, was Sie berücksichtigen müssen, wenn Sie sich entscheiden, Ihre vorhandenen Skype for Business Server- oder Exchange Server bereitstellungen auf die neueste Version oder auf Skype for Business Online oder Exchange Online zu migrieren.
ms.openlocfilehash: edc6256bc9e366b4ee75a637c41141ec3d435da2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596119"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planen der Migration von Skype for Business Server und Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Thema wird erläutert, was Sie berücksichtigen müssen, wenn Sie ihre vorhandenen Skype for Business Server oder Exchange Server-Bereitstellungen zu Exchange Online migrieren möchten. Was Sie migrieren können und wann, hängt stark davon ab, was Sie in Ihrer Organisation bereits eingerichtet haben.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Featureänderungen in Exchange 2019 und Skype for Business Server 2019

Mit Exchange 2019 und Skype for Business Server 2019 nehmen wir einige Änderungen an den features vor, die wir unterstützen.

### <a name="unified-messaging-support-in-exchange-2019"></a>Unified Messaging-Unterstützung in Exchange 2019

Unified Messaging (UM) ist in Exchange 2019 veraltet. Dies bedeutet, dass Exchange 2019 nicht mehr die folgenden Features bietet:

- Voicemail
- Automatische Telefonzentrale

Wenn Sie die UM-Rolle in Exchange 2013 oder den UM-Dienst in Exchange 2016 bereitgestellt haben und auf Exchange 2019 aktualisieren möchten, müssen Sie Ihre Voicemail in Microsoft 365 oder Office 365 zum Microsoft Cloud-Voicemail dienst migrieren. Wenn Sie Ihre Voicemail zu Cloud-Voicemail migrieren möchten, sehen Sie sich den Abschnitt [Exchange 2013/Exchange 2016 und Skype for Business 2015 zu Exchange 2019 und Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) an.
> [!IMPORTANT]
> Wenn Benutzer auf Ihren Exchange 2013- oder Exchange 2016-Servern UM-aktivierte Postfächer haben, verschieben Sie sie nicht in Exchange 2019, bevor Sie Ihr Skype for Business-Server auf Skype for Business Server 2019 aktualisieren und Benutzer zu ihnen verschieben, um einen Sprachnachrichtenausfall zu vermeiden.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Pbx-Unterstützung in Exchange 2019 und Skype for Business Server 2019

Cloud-Voicemail bietet keine Sprachnachrichtenfunktionen für Nebenstellenanlagen (Private Branch Exchanges, PBX). Wenn Sie Exchange Server Unified Messaging für Nebenstellenanlagen verwenden und ein Upgrade auf Exchange Server 2019 durchführen möchten, müssen Sie eine der drei Optionen übernehmen, die im Blogbeitrag ["Neues Datum"](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) aufgeführt sind, um die Unterstützung für Session Border Controller in Exchange Online Unified Messaging im [Exchange Teamblog](https://blogs.technet.microsoft.com/exchange/)einzustellen.

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online UM-Unterstützung in Skype for Business Server 2019

Mit Skype for Business Server 2019 wechseln wir von Exchange Online UM zu Cloud-Voicemail. Wenn ein Benutzer auf einen Skype for Business 2019-Server verschoben wird, verwendet er automatisch Cloud-Voicemail, wenn er für gehostete Voicemail konfiguriert ist. Wenn Sie derzeit Exchange Online UM verwenden, müssen Sie nur einen Benutzer in Skype for Business Server 2019 verschieben, um mit der Verwendung von Cloud-Voicemail zu beginnen. Es gibt jedoch einige Änderungen an der Funktionalität, die Sie beachten müssen:

- Die automatische Telefonzentrale der Organisation ist der Ersatz für die automatische Telefonzentrale in Exchange Online UM.
- Benutzer-Voicemaileinstellungen in Outlook im Web gelten nicht für Cloud-Voicemail.

## <a name="on-premises-um-migration-scenarios"></a>Lokale UM-Migrationsszenarien

Wir unterstützen die folgenden Szenarien, in denen Sie Benutzer sowohl zu Exchange 2019 als auch zu Cloud-Voicemail migrieren können.

- Exchange 2013/Exchange 2016 und Skype for Business Server 2015 bis Exchange 2019 und Skype for Business Server 2019
- Skype for Business Server 2015 bis Skype for Business Server 2019 mit Exchange 2013/Exchange 2016

In den folgenden Szenarien ist es erforderlich, dass keine PBX- oder SBC-Konfigurationen im Rahmen Der aktuellen Bereitstellung vorhanden sind, und es wird davon ausgegangen, dass SIE UM auf Ihren lokalen Exchange Servern konfiguriert haben. Bei jeder dieser Lösungen wird auch davon ausgegangen, dass Sie sich entschieden haben, eine Hybridbereitstellung zwischen Ihren lokalen Skype for Business Servern und Microsoft 365 oder Office 365 zu konfigurieren. Weitere Informationen zu Skype for Business Hybridbereitstellungen finden Sie unter Planen der [Hybridkonnektivität.](plan-hybrid-connectivity.md)

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 und Skype for Business 2015 bis Exchange 2019 und Skype for Business 2019

In diesem Szenario möchten Sie Ihre vorhandenen Server Exchange 2013, Exchange 2016 und Skype for Business 2015 zu Exchange 2019 und Skype for Business 2019 migrieren.

Wie bereits in diesem Thema erwähnt, enthält Exchange 2019 den UM-Dienst nicht mehr. Dies bedeutet, dass Sie für alle Postfächer, die Sie auf Exchange 2019 verschieben möchten, Cloud-Voicemail verwenden müssen, um die vom UM-Dienst bereitgestellte Funktionalität zu ersetzen. Wenn Sie Skype for Business Server 2019 und eine Hybridbereitstellung zwischen dieser und Microsoft 365 oder Office 365 einrichten, ersetzt Cloud-Voicemail diese Exchange UM-Voicemaildienste.

Die Reihenfolge, in der Sie Benutzer nach Exchange 2019 und Skype for Business Server 2019 verschieben, ist wichtig, um sicherzustellen, dass die Voicemailfunktion für alle Benutzer verfügbar bleibt. Wo Voicemail verarbeitet wird, hängt auch davon ab, wo sich die Exchange und Skype for Business Postfächer und Benutzer befinden. Sehen Sie sich die folgende Tabelle an, um zu sehen, welche Kombinationen von Exchange und Skype for Business Server unterstützt werden und wo Voicemail verarbeitet wird.

| Postfach befindet sich auf:            | Benutzer befindet sich auf Skype for Business Server 2015 | Benutzer befindet sich auf Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | Nicht unterstützt                           | Cloud-Voicemail                          |

Bevor Sie mit der Migration zu Skype for Business Server 2019 und Exchange 2019 beginnen, sollten Sie Folgendes bedenken:

- Cloud-Voicemail unterstützt keine automatische Telefonzentrale der Organisation bei GA. Wenn Postfächer in Cloud-Voicemail über die automatische Telefonzentrale weiterhin verfügbar sein sollen, müssen Sie mindestens einen Exchange 2013- oder Exchange 2016-Server mit der UM-Rolle oder dem UM-Dienst verfügbar halten.
- Sie müssen mindestens einen Skype for Business 2019-Server einrichten **und** Benutzer auf diesen Server verschieben, bevor Sie ihre Postfächer auf Exchange 2019 verschieben. Andernfalls können diese Postfächer keine Voicemailnachrichten empfangen.
- An Voicemail gesendete Anrufe werden an Cloud-Voicemail weitergeleitet, wo sie aufgezeichnet werden. Nachdem der Anruf beendet wurde, wird die Voicemailnachricht an das Postfach des Empfängers auf dem lokalen Server Exchange 2019 gesendet. Sie müssen diesen VoIP-Datenverkehr berücksichtigen, wenn Sie ermitteln, ob Ihre Internetverbindung ausreicht, um Cloud-Voicemail zu unterstützen.

Hier sind die allgemeinen Schritte zum Abschließen dieser Migration.

1. Installieren und konfigurieren Sie Skype for Business Server 2019 auf einem neuen Server.
2. Aktualisieren Sie ihre Hybridbereitstellungskonfiguration, um den neuen Skype for Business 2019-Server einzuschließen.
3. Installieren und konfigurieren Sie Exchange Server 2019 auf einem neuen Server.
4. Verschieben Sie Benutzer von Ihrem Skype for Business 2015-Server zu Ihrem Skype for Business 2019-Server.
5. Legen Sie die Richtlinie für gehostete Voicemail für jeden Benutzer fest, der in Skype for Business Server 2019 verschoben wurde, um Cloud-Voicemail zu verwenden.
6. Verschieben Sie Postfächer von Ihrem Exchange 2013- oder Exchange 2016-Server auf Ihren Exchange 2019-Server.
7. Setzen Sie Ihre Skype for Business 2015-Server außer Betrieb, nachdem der letzte Benutzer von ihnen entfernt wurde.
8. Setzen Sie Ihre Exchange 2013- oder Exchange 2016-Server außer Betrieb, nachdem das letzte Postfach von ihnen entfernt wurde.

    > [!IMPORTANT]
    > Wenn Sie eine automatische Telefonzentrale verwenden, sollten Sie mindestens eine Exchange 2013 oder Exchange 2016 ausführen und verfügbar halten.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 bis Skype for Business Server 2019 mit Exchange 2013/Exchange 2016

In diesem Szenario möchten Sie Ihren vorhandenen Skype for Business 2015-Server zu Skype for Business Server 2019 migrieren, aber auf Exchange 2013 oder Exchange 2016 bleiben.

Wenn Skype for Business Server 2015 und Skype for Business Server 2019 in derselben Organisation vorhanden sind, arbeiten sie nahtlos mit Exchange UM und Cloud-Voicemail zusammen, um sicherzustellen, dass Voicemail ordnungsgemäß an Exchange Postfächer übermittelt wird. Ob Exchange UM oder Cloud-Voicemail die Voicemail verarbeitet, hängt davon ab, ob sich der Benutzer Skype for Business Server 2015 oder Skype for Business Server 2019 befindet:

- Wenn sich ein Benutzer Skype for Business Server 2015 befindet, verarbeitet Exchange UM die Voicemailnachricht.
- Wenn sich ein Benutzer Skype for Business Server 2019 befindet, verarbeitet Cloud-Voicemail die Voicemailnachricht.

Unabhängig davon, ob Exchange UM oder Cloud-Voicemail die Voicemailnachricht verarbeitet, wird die Nachricht im postfach Exchange des Benutzers gespeichert.

Bevor Sie mit der Migration zu Skype for Business Server 2019 beginnen, sollten Sie Folgendes bedenken:

- Cloud-Voicemail unterstützt keine automatische Telefonzentrale der Organisation bei GA. Wenn Postfächer in Cloud-Voicemail über die automatische Telefonzentrale weiterhin verfügbar sein sollen, müssen Sie mindestens einen Exchange 2013- oder Exchange 2016-Server mit der UM-Rolle oder dem UM-Dienst verfügbar halten.
- An Voicemail gesendete Anrufe werden an Cloud-Voicemail weitergeleitet, wo sie aufgezeichnet werden. Nachdem der Anruf beendet wurde, wird die Voicemailnachricht an das Postfach des Empfängers auf dem lokalen Exchange Server gesendet. Sie müssen diesen VoIP-Datenverkehr berücksichtigen, wenn Sie ermitteln, ob Ihre Internetverbindung ausreicht, um Cloud-Voicemail zu unterstützen.

Hier sind die allgemeinen Schritte zum Abschließen dieser Migration.

1. Installieren und konfigurieren Sie Skype for Business Server 2019 auf einem neuen Server.
2. Aktualisieren Sie ihre Hybridbereitstellungskonfiguration, um den neuen Skype for Business 2019-Server einzuschließen.
3. Verschieben Sie Benutzer von Ihrem Skype for Business 2015-Server zu Ihrem Skype for Business 2019-Server.
4. Legen Sie die Richtlinie für gehostete Voicemail für jeden Benutzer fest, der in Skype for Business Server 2019 verschoben wurde, um Cloud-Voicemail zu verwenden.
5. Setzen Sie Ihre Skype for Business 2015-Server außer Betrieb, nachdem der letzte Benutzer von ihnen entfernt wurde.

    > [!IMPORTANT]
    > Wenn Sie eine automatische Telefonzentrale verwenden, sollten Sie mindestens eine Exchange 2013 oder Exchange 2016 ausführen und verfügbar halten.
