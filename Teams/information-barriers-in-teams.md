---
title: Informationen Barrieren in Microsoft-Teams – Vorschau
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: Informationen Sie zu Informationen Barrieren und deren Auswirkungen auf Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a529784ba9968835ce5fb9d8e8648022e46beda5
ms.sourcegitcommit: f29c0c41dc40f7e968a675d2cf10ef17d7e784da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506750"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a>Informationen Barrieren in Microsoft-Teams – Vorschau

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

Informationen Hindernisse werden Richtlinien, die ein Administrator konfigurieren können, um zu verhindern, dass Personen oder Gruppen miteinander kommunizieren. Dies ist nützlich, wenn Sie beispielsweise einer Abteilung Informationen, die mit anderen Abteilungen gemeinsam genutzt werden sollte nicht behandelt wird oder eine Gruppe bei der Kommunikation mit externen Kontakten gehindert werden muss.

> [!NOTE]
> - Informationen Grenze Gruppen können nicht konstant erstellt werden.
> - Verwenden zum Hinzufügen von Benutzern Bots wird für Version 1 nicht unterstützt.

Informationsrichtlinien Grenze verhindert, dass auch Lookups und Erkennung. Das heißt, wenn Sie versuchen, mit einer anderen Person kommunizieren nicht dem eine Verbindung hergestellt werden soll, werden Sie der Benutzer in der Personenauswahl nicht gefunden.

## <a name="background"></a>Hintergrund

Der primäre Treiber für Informationen Hindernisse stammen aus Finanzdienstleister. Die finanziellen Branche behördlichen Behörde ([FINRA]( http://www.finra.org/)) überprüft Informationen Barrieren und Konflikte von Interesse in Firmen und erfahren Sie, wie zum Verwalten von solche Konflikte (FINRA 2241, [Behördlichen-Anmerkung zur Forderung Research 15 31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>Wann sollte ich Informationen Hindernisse werden verwendet?

Sie sollten Informationen Barrieren in solchen Situationen verwenden:

- Ein Team muss verhindert werden kommunizieren oder Freigeben von Daten mit einem bestimmten anderen Team.
- Ein Team muss nicht kommunizieren oder Freigeben von Daten für Benutzer außerhalb des Teams.

Der Informationsdienst Grenze Richtlinie Auswertung bestimmt, ob eine Kommunikation mit Informationsrichtlinien Grenze entspricht. 

## <a name="managing-information-barrier-policies"></a>Verwalten von Informationsrichtlinien Grenze

Grenze Informationsrichtlinien werden mit Sicherheit & Compliance Center (SCC) PowerShell-Cmdlets verwaltet. Weitere Informationen zur Verwendung dieser Cmdlets, [Melden Sie sich hier](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

> [!IMPORTANT]
> Vor dem Einrichten oder Richtlinien, **müssen Sie bereichsbezogenen Verzeichnissuche finden, in der Microsoft-Teams aktivieren**definieren. Warten Sie mindestens 24 Stunden nach der Aktivierung bereichsbezogenen Verzeichnissuche finden, vor dem Einrichten oder Richtlinien für Informationen Hindernisse definieren.

## <a name="information-barriers-administrator-role"></a>Informationen Hindernisse Administratorrolle

Informationen Hindernisse Administratorrolle ist verantwortlich für die Verwaltung von Informationsrichtlinien-Grenze. Weitere Informationen zu dieser Rolle und zur Teilnahme an der Vorschau, [Registrieren Sie sich hier](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

## <a name="when-are-information-barrier-policies-checked"></a>Wann sind Informationsrichtlinien Grenze überprüft?

Grenze Informationsrichtlinien werden überprüft, wenn die folgenden Ereignisse Teams stattfinden:

- **Ein Team Mitglieder hinzugefügt werden** - Wenn Sie einen Benutzer zu einem Team, die Richtlinie des Benutzers hinzufügen müssen gegen die Grenze Informationsrichtlinien der anderen Teammitglieder ausgewertet werden. Nachdem der Benutzer erfolgreich hinzugefügt wurde, kann der Benutzer alle Funktionen im Team ohne weitere Überprüfung durchführen. Wenn die Richtlinie des Benutzers werden blockiert an das Team hinzugefügt wird, wird der Benutzer nicht bei der Suche angezeigt.
- **Ein neuer Chat angefordert wird** - jedes Mal ein neuer Chat zwischen zwei oder mehr Benutzer angefordert wird der Chat ausgewertet wird, stellen Sie sicher, dass es Grenze Informationsrichtlinien verletzen nicht zur Verfügung. Wenn die Unterhaltung eine Grenze Informationsrichtlinien verstößt gegen die Unterhaltung wird nicht eingeleitet, und es wird eine Fehlermeldung angezeigt.
- **Ein Benutzer zur Teilnahme an einer Besprechung eingeladen** -, wenn ein Benutzer zur Teilnahme an einer Besprechung eingeladen wird, die Richtlinie des Benutzers gegen die Richtlinien der anderen Teammitglieder ausgewertet wird und ist eine Verletzung, wird der Benutzer die Teilnahme an der Besprechung nicht zulässig sein und eine Fehlermeldung wird angezeigt.
- **Ein Bildschirm gemeinsam genutzt wird, zwischen zwei oder mehr Benutzer** - ist jederzeit einen Bildschirm zwischen mindestens zwei Benutzern gemeinsam verwendet, die Freigabe Bildschirm ausgewertet werden muss, um sicherzustellen, dass sie nicht die Grenze Informationsrichtlinien anderer Benutzer verletzen. Wenn eine Grenze Informationsrichtlinien verletzt wird, die Freigabe Bildschirm wird nicht zulässig, und eine Fehlermeldung wird angezeigt.
- **Ein Benutzer einen Anruf (VOIP) in Teams tätigt** - wird jedes Mal, wenn ein Anruf von einem Benutzer an einen anderen Benutzer oder Gruppe von Benutzern, den Anruf initiiert wird ausgewertet, stellen Sie sicher, dass sie nicht die Grenze Informationsrichtlinien Oher Teammitglieder verletzen. Wenn eine Verletzung vorhanden ist, wird der VoIP-Anruf blockiert.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>Was geschieht mit vorhandenen Chat Threads, wenn eine Richtlinie geändert wird?

Wenn die Informationen Grenze Richtlinie Admin ändert die Richtlinie oder eine Änderung der Richtlinie startet in Kraft aufgrund eines Benutzers Auftrag ändern oder einem ähnlichen Grund der Grenze Richtlinie Evaluation Dienst automatisch sucht die Member, um sicherzustellen, dass Teammitglieder werden alle Richtlinien nicht verletzen. 

Es ist eine vorhandene Chat oder andere Kommunikation zwischen Benutzern, und eine neue Richtlinie festgelegt ist, oder eine vorhandene Richtlinie geändert wird, wertet der Dienst vorhandenen Communications, um sicherzustellen, dass sie "werden nicht" sozusagen (nicht mehr zulässig): 

- **1:1-Chat** - Kommunikation zwischen zwei Benutzern ist nicht mehr zulässig (sofern eine Richtlinie Blockieren der Kommunikation für eine oder beide Benutzer angewendet wird), weitere Kommunikation wird blockiert und die Chat-Unterhaltung wird als schreibgeschützt.
- **Gruppenchat** - Wenn Kommunikation eines Benutzers zur Gruppe nicht mehr zulässig ist (z. B., wenn ein Benutzer Aufträge ändert), der Benutzer zusammen mit den anderen Benutzern, die die Richtlinie verletzen werden, von Gruppenchat entfernt kann und weitere Kommunikation mit der Gruppe nicht werden zulässig. Der Benutzer kann weiterhin sehen alte Unterhaltungen (die schreibgeschützt sein werden), werden jedoch nicht sehen, oder alle neuen Gespräche mit der Gruppe teilnehmen. Wenn die neue oder geänderte Richtlinie verhindert die Kommunikation an mehrere Benutzer angewendet wird, können der Benutzer, die von der Richtlinie betroffen sind aus Gruppenchat entfernt werden. Sie können weiterhin alte Unterhaltungen anzeigen. 
- **Team** - alle Benutzer, die aus der Gruppe entfernt wurden aus dem Team entfernt werden und werden nicht sehen oder vorhandene oder neue Unterhaltungen teilnehmen.

## <a name="required-licenses-and-permissions"></a>Erforderlichen Lizenzen und Berechtigungen

Die Informationen Grenze Features ist derzeit in privaten Vorschau. Wenn diese Features im Allgemeinen verfügbar sind, können sie wie in Abonnements, aufgenommen werden:

- Microsoft 365 E5
- Office 365 E5
- Office 365 erweiterte Compliance
- Microsoft 365 E5 Compliance

Weitere Informationen, einschließlich der Pläne und zu Preisen finden Sie unter [Compliance-Lösungen](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).