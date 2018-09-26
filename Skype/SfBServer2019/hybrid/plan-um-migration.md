---
title: Planen von Skype für Business Server und Exchange Server-migration
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: In diesem Thema wird behandelt, was Sie berücksichtigen müssen, wenn Sie Ihre vorhandenen Skype für Business Server oder Exchange Server-Bereitstellungen auf die neueste Version oder Skype für Business Online oder Exchange Online migrieren möchten.
ms.openlocfilehash: 25d0e275110df57747679efec46a77571259a3d4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027256"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planen von Skype für Business Server und Exchange Server-migration

[!INCLUDE [disclaimer](../disclaimer.md)]

In diesem Thema wird behandelt, was Sie berücksichtigen müssen, wenn Sie Ihre vorhandenen Skype für Business Server oder Exchange Server-Bereitstellungen auf die neueste Version oder Skype für Business Online oder Exchange Online migrieren möchten. Was können Sie migrieren, und zu welchen Zeitpunkten, stark hängt, was Sie bereits in Ihrer Organisation eingerichtet haben. In der Vorschau sind wir Konzentration auf die Unterstützung von ein paar bestimmter Szenarien mit zusätzlicher Szenarios verfügbar unter allgemeine Verfügbarkeit (GA).

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Featureänderungen Sie in Exchange 2019 und Skype für Business Server 2019

Mit Exchange 2019 und Skype für Business Server 2019 machen wir einige Änderungen auf die Features unterstützt.

### <a name="unified-messaging-support-in-exchange-2019"></a>Unified Messaging-Unterstützung in Exchange 2019

Unified Messaging (UM) ist in Exchange 2019 veraltet. Dies bedeutet, dass Exchange 2019 nicht mehr die folgenden Features bietet:

- Voicemail
- Automatische Telefonzentrale

Wenn Sie bereitgestellt die UM-Rolle in Exchange 2013 oder den UM-Dienst im Exchange 2016 haben haben, und Sie auf Exchange 2019 aktualisieren möchten, müssen Sie Ihre Voicemail-Ansage an den Microsoft-Cloud-Voicemail-Dienst in Office 365 zu migrieren. Wenn Sie Ihre Voicemail-Ansage an die Voicemail Cloud migrieren möchten, sehen Sie sich im Abschnitt [Exchange 2013/Exchange 2016 und Skype für Business 2015 Exchange 2019 und Skype für Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) weiter unten.
> [!IMPORTANT]
> Wenn Benutzer auf Ihren Servern Exchange 2013 oder 2016 Exchange UM-aktivierten Postfächer vorhanden sind, verschieben Sie nicht sie in Exchange 2019 vor dem upgrade Ihrer Skype für Unternehmensserver auf Skype für Business Server 2019 und Verschieben von Benutzern in einer Voicemessaging-Ausfall vermieden.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>PBX-Unterstützung in Exchange 2019 und Skype für Business Server 2019

Cloud-Voicemail zur Voicemessaging-Funktionalität für Nebenstellenanlagen (PBX) nicht Verfügung. Wenn Sie Exchange Server Unified Messaging für Nebenstellenanlagen und Sie auf Exchange Server 2019 aktualisieren möchten, müssen Sie eine der drei Optionen aufgelistet in den Blogbeitrag [Neues Datum für die Einstellung der Unterstützung für Session Border Controller im Exchange einführen Online Unified Messaging](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) im [Exchange-Teamblog](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online UM Unterstützung in Skype für Business Server 2019

Mit Skype für Business Server 2019 verschieben wir von Exchange Online UM an die Voicemail Cloud. Wenn ein Benutzer auf einen Skype für Business 2019 Server verschoben wird, werden automatisch gestartet mit Cloud Voicemail für gehostete Voicemail konfiguriert. Wenn Sie derzeit Exchange Online UM verwenden, müssen Sie nicht als verschieben ein Benutzers für die Skype für Business Server 2019 für den Einstieg Cloud Voicemail nichts. Es gibt jedoch einige Änderungen an Funktionen, die Sie berücksichtigen müssen:

- Für die Vorschau nicht Organisationseinheit automatische Telefonzentralen (Ersatz für in Exchange Online UM-Telefonzentrale) zur Verfügung. Organisatorische automatische Telefonzentrale wird bei GA verfügbar sein.
- Benutzer Voicemail-Einstellungen in Outlook im Web gelten nicht an die Cloud Voicemail.

## <a name="on-premises-um-migration-scenarios"></a>Lokale UM-Migrationsszenarien

In der Vorschau haben wir die folgenden Szenarien unterstützen, die Sie migrieren von Benutzern zu Exchange 2019 und an die Cloud Voicemail aktiviert wird. Unter GA Unterstützung wir weiterer Szenarien, die Sie von zusätzlichen Versionen von Exchange und Skype für Business Server migrieren können. Wir werden auch zusätzliche Features wie Organisationseinheit automatische Telefonzentrale bieten.

- Exchange 2013/Exchange 2016 und Skype für Business Server 2015 zu Exchange 2019 und Skype für Business Server 2019
- Skype für Business Server 2015 Skype für Business Server 2019 mit Exchange 2013/Exchange 2016

Die folgenden Szenarien erfordern, dass keine Nebenstellenanlage oder der SBC-Konfigurationen als Teil der aktuellen Bereitstellung vorhanden und wird davon ausgegangen, dass Sie UM auf den lokalen Exchange-Servern konfiguriert haben. Jede dieser Lösung wird davon ausgegangen, dass Sie sich entschieden haben, konfigurieren Sie eine hybridbereitstellung zwischen Ihrer lokalen Skype für Business Server und Office 365. Weitere Informationen zu Skype für hybridbereitstellungen Business finden Sie unter [Skype für Business hybridlösungen](hybrid-solutions.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 und Skype für Business 2015 zu Exchange 2019 und Skype für Business 2019

In diesem Szenario möchten Sie Ihre vorhandenen Exchange 2013, Exchange 2016, Skype 2015 Business Server zum Exchange 2019 wird und Skype für Business 2019 migrieren.

Wie weiter oben in diesem Thema erwähnt, enthalten den UM-Dienst Exchange 2019 nicht mehr. Dies bedeutet, dass für alle Postfächer, die zu verschiebende zu Exchange 2019, müssen Sie Cloud Voicemail verwenden, um die Funktionalität zu ersetzen, die von den UM-Dienst bereitgestellt wurde. Wenn Sie Skype für Business Server 2019 und eine hybridbereitstellung zwischen der Rollengruppe und Office 365 einrichten, ersetzt Cloud Voicemail diese Exchange UM-Voicemail-Dienste.

Die Reihenfolge, in der Sie Benutzer in Exchange 2019 und Skype für Business Server 2019 verschieben, ist wichtig, um sicherzustellen, dass Voicemail-Funktionalität für alle Benutzer verfügbar bleibt. Wo Voicemail verarbeitet werden ist ebenfalls davon, wo sich die Exchange und Skype für Business Postfächer und Benutzer befinden. Sehen Sie sich in der folgenden Tabelle sehen Sie, welche Kombinationen von Exchange und Skype für Business Server unterstützt werden, und wo Voicemail verarbeitet werden.

| Postfach auf:            | Benutzer, die sich nicht auf Skype für Business Server 2015 | Benutzer, die sich nicht auf Skype für Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Cloud-Voicemail                          |
| Exchange 2019                  | Nicht unterstützt                           | Cloud-Voicemail                          |

Bevor Sie mit die Migration zu Skype für Business Server 2019 und Exchange 2019 beginnen, behalten Sie Folgendes beachten:

- Cloud-Voicemail unterstützt keine Organisationseinheit automatische Telefonzentrale in Vorschau. Postfächer, die an die Cloud Voicemail weiterhin über die automatische Telefonzentrale verfügbar sein verschoben werden soll, müssen Sie mindestens einen Exchange 2013 oder 2016 Exchange-Server mit der UM-Rolle oder einen Dienst verfügbar zu halten.
- Sie müssen mindestens einen Skype für Business 2019 Server **und** Move-Benutzer für den betreffenden Server einrichten, bevor Sie ihre Postfächer in Exchange 2019 verschieben. Ist dies nicht der Fall, führt zu dieser Postfächer keine Voicemailnachrichten empfangen wird.
- Anrufe an die Voicemail gesendet werden an die Cloud Voicemail weitergeleitet, in dem aufgezeichnet werden. Nach Beendigung des Anrufs wird die Voicemailnachricht an das Postfach des Empfängers auf dem lokalen Exchange-2019 Server gesendet. Sie müssen berücksichtigen diese VoIP-Datenverkehr bei bestimmen, ob die Verbindung zum Internet ausreichend, um Voicemail Cloud unterstützt wird.

Hier sind die allgemeinen Schritte dieser Migration abschließen.

1. Installieren und Konfigurieren von Skype für Business Server 2019 auf einem neuen Server.
2. Aktualisieren Sie die Konfiguration Ihrer Hybriden Bereitstellung zum Einschließen von der neuen Skype für Business 2019 Server.
3. Installieren und Konfigurieren von Exchange Server 2019 auf einem neuen Server.
4. Verschieben Sie Benutzer von Ihrer Skype für Business 2015 Server in Ihrer Skype für Business 2019 Server.
5. Festlegen der gehosteten voicemailrichtlinie für jeden Benutzer verschoben und Skype für Business Server 2019 Cloud Voicemail verwenden.
6. Verschieben von Postfächern aus Ihrem Exchange 2013 oder 2016 Exchange-Server auf Ihrem Exchange 2019 Server.
7. Außer Betrieb nehmen Sie Ihre Skype für 2015 Business Server, nachdem die letzte Benutzer von sie verschoben wurde.
8. Außer Betrieb nehmen Sie Ihren Exchange 2013 oder 2016 Exchange-Servern, nachdem das letzte Postfach von sie verschoben wurde.

    > [!IMPORTANT]
    > Wenn Sie auf eine automatische Telefonzentrale angewiesen, lassen Sie mindestens einen Exchange 2013 oder Exchange 2016 ausgeführt wird und verfügbar.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype für Business Server 2015 Skype für Business Server 2019 mit Exchange 2013/Exchange 2016

In diesem Szenario soll zum Migrieren Ihrer vorhandenen Skype für Business 2015 Server zu Skype für Business Server 2019 jedoch auf Exchange 2013 oder Exchange 2016 bleiben.

Wenn Skype für Business Server 2015 und Skype für Business Server 2019 in derselben Organisation koexistieren, deren Funktionsweise nahtlos mit Exchange UM und Cloud-Voicemail, um sicherzustellen, dass Voicemail wird ordnungsgemäß an Exchange-Postfächer übermittelt. Ob Exchange UM oder Cloud Voicemail die Voicemail verarbeitet, hängt davon ab, gibt an, ob der Benutzer auf Skype für Business Server 2015 oder Skype für Business Server 2019 befindet:

- Wenn ein Benutzer auf Skype für Business Server 2015 befindet, wird die Voicemailnachricht Exchange UM verarbeitet.
- Wenn ein Benutzer auf Skype für Business Server 2019 befindet, wird die Cloud Voicemail der Voicemailnachricht verarbeitet.

Unabhängig davon, ob Exchange UM oder Cloud Voicemail der Voicemailnachricht verarbeitet wird die Nachricht im Exchange-Postfach des Benutzers gespeichert werden.

Bevor Sie mit die Migration zu Skype für Business Server 2019 beginnen, behalten Sie Folgendes beachten:

- Cloud-Voicemail unterstützt keine Organisationseinheit automatische Telefonzentrale in Vorschau. Postfächer, die an die Cloud Voicemail weiterhin über die automatische Telefonzentrale verfügbar sein verschoben werden soll, müssen Sie mindestens einen Exchange 2013 oder 2016 Exchange-Server mit der UM-Rolle oder einen Dienst verfügbar zu halten.
- Anrufe an die Voicemail gesendet werden an die Cloud Voicemail weitergeleitet, in dem aufgezeichnet werden. Nach Beendigung des Anrufs wird die Voicemailnachricht an das Postfach des Empfängers auf dem lokalen Exchange-Server gesendet. Sie müssen berücksichtigen diese VoIP-Datenverkehr bei bestimmen, ob die Verbindung zum Internet ausreichend, um Voicemail Cloud unterstützt wird.

Hier sind die allgemeinen Schritte dieser Migration abschließen.

1. Installieren und Konfigurieren von Skype für Business Server 2019 auf einem neuen Server.
2. Aktualisieren Sie die Konfiguration Ihrer Hybriden Bereitstellung zum Einschließen von der neuen Skype für Business 2019 Server.
3. Verschieben Sie Benutzer von Ihrer Skype für Business 2015 Server in Ihrer Skype für Business 2019 Server.
4. Festlegen der gehosteten voicemailrichtlinie für jeden Benutzer verschoben und Skype für Business Server 2019 Cloud Voicemail verwenden.
5. Außer Betrieb nehmen Sie Ihre Skype für 2015 Business Server, nachdem die letzte Benutzer von sie verschoben wurde.

    > [!IMPORTANT]
    > Wenn Sie auf eine automatische Telefonzentrale angewiesen, lassen Sie mindestens einen Exchange 2013 oder Exchange 2016 ausgeführt wird und verfügbar.