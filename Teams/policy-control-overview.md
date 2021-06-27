---
title: Übersicht über die Richtliniensteuerung für Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Eine Übersicht über die Richtliniensteuerungen für Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed0e5aa3a39147238bf0ade57df509a31f0f13e8
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142811"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Übersicht über die Richtliniensteuerung für Microsoft Teams

Microsoft ist bestrebt, Ihnen die Informationen und Kontrollen zur Verfügung zu stellen, die Sie benötigen, um Entscheidungen darüber zu treffen, wie Ihre Daten bei der Verwendung von Microsoft Teams, einem Bestandteil von Microsoft 365, erfasst und verwendet werden.

Dieser Artikel soll Ihnen Informationen über Kontrollmechanismen für den Datenschutz für die folgenden Bereiche liefern:

- **Diagnosedaten**, die gesammelt und an Microsoft gesendet werden, um die Verwendung von Teams- und Office-Software auf Computern mit Windows in Ihrer Organisation zu dokumentieren.
- **Verbundene Erfahrungen**, die cloudbasierte Funktionen nutzen, um Ihnen und Ihren Benutzern erweiterte Teams- und Office-Features zur Verfügung zu stellen.

Im Rahmen dieser Änderungen gibt es neue und aktualisierte Benutzeroberflächenelemente (UI) und Richtlinieneinstellungen.

> [!IMPORTANT]
> Weitere Informationen finden Sie in der [Übersicht über Datenschutzkontrollen für Microsoft 365 Apps for Enterprise](/deployoffice/privacy/overview-privacy-controls).

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>Diagnosedaten, die von Microsoft 365 Apps for Enterprise an Microsoft gesendet werden

Diagnosedaten werden verwendet, um:

- Teams sicher und auf dem neuesten Stand zu halten.
- Probleme zu erkennen, zu diagnostizieren und zu beheben.
- Produktverbesserungen vorzunehmen.

Ein Beispiel für einige der gesammelten Daten:

- Anwendungssprache
- Benutzertyp
- Buildversion des Betriebssystems

## <a name="clients-that-adhere-to-diagnostic-controls"></a>Clients, für die Diagnosesteuerelemente gelten

Die folgenden Clients halten sich an Diagnosesteuerelemente und senden Daten:

- iOS
- Android
- Desktop (nur die Komponente, die die Win32-API verwendet)

Eine Liste der erforderlichen Diagnosedatenereignisse und deren Eigenschaften finden Sie in den folgenden Artikeln:

- [Erforderliche mobile Diagnosedaten für Microsoft Teams](policy-control-diagnostic-data-mobile.md)
- [Erforderliche Desktop-Diagnosedaten für Microsoft Teams](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Diagnosedaten, die von der Teams-App an Microsoft gesendet werden

Diese Diagnosedaten werden gesammelt und an Microsoft gesendet, um die Verwendung von Teams-Software auf Computern mit Windows in Ihrer Organisation zu dokumentieren.

Es gibt drei Ebenen von Diagnosedaten für die Teams-Software, aus denen Sie wählen können:

- **Erforderlich** Die Mindestdaten, die erforderlich sind, um sicherzustellen, dass Office auf dem Gerät, auf dem es installiert ist, auf dem neuesten Stand ist sowie sicher und erwartungsgemäß funktioniert.
- **Optional** Zusätzliche Daten, die uns helfen, Produktverbesserungen vorzunehmen und erweiterte Informationen liefern, die uns helfen, Probleme zu erkennen, zu diagnostizieren und zu beheben.
- **Weder noch** Es werden keine Diagnosedaten über die auf dem Gerät des Benutzers ausgeführte Teams-Software gesammelt und an Microsoft gesendet. Diese Option schränkt jedoch unsere Möglichkeiten zur Erkennung, Diagnose und Behebung von Problemen erheblich ein, auf die Ihre Benutzer bei der Verwendung von Teams stoßen könnten.

Erforderliche Diagnosedaten können z. B. Informationen über die auf dem Gerät installierte Version des Teams-Client sein oder Informationen beinhalten, die darauf hindeuten, dass die Teams-Anwendung beim Versuch, an einer Besprechung teilzunehmen, abstürzen. Optionale Diagnosedaten können Informationen über die zum Starten eines Telefonanrufs erforderliche Zeit beinhalten, was auf ein Problem mit der Verbindung oder mit der Netzwerkleistung hinweisen könnte.

Wenn Sie sich dafür entscheiden, uns optionale Diagnosedaten zu senden, werden auch die erforderlichen Diagnosedaten mitgeliefert.

Als Administrator für Ihr Unternehmen können Sie anhand einer Richtlinieneinstellung auswählen, welche Ebene von Diagnosedaten an uns gesendet wird. Optionale Diagnosedaten werden an Microsoft gesendet, es sei denn, Sie ändern die Einstellung. Die Bereitstellung optionaler Diagnosedaten ermöglicht es dem Office-Entwicklerteam von Microsoft, Probleme zu erkennen, zu diagnostizieren und zu beheben, um die Auswirkungen auf Ihr Unternehmen zu minimieren. 

Zum Auswählen der Ebene für die an uns gesendeten Diagnosedaten verwenden Sie den [Office-Cloudrichtliniendienst](/deployoffice/overview-office-cloud-policy-service), und konfigurieren Sie die Richtlinieneinstellung *Ebene der von Office an Microsoft gesendeten Software-Diagnosedaten konfigurieren*. Dies ist dieselbe Richtlinieneinstellung, mit der konfiguriert wird, welche Ebene von Diagnosedaten durch andere Office-Apps (wie Word, Excel und PowerPoint) gesendet wird, die in Microsoft 365 Apps for Enterprise enthalten sind.

Wenn Benutzer mit den organisatorischen Anmeldeinformationen (auch als Geschäfts-, Schul- oder Unikonto bezeichnet) bei Teams angemeldet sind, können sie die Diagnosedatenebene für ihre Geräte nicht ändern.

Diese Diagnosedaten enthalten keine Namen von Benutzern, ihre E-Mail-Adressen oder andere Benutzerinhalte, wie z. B. in Teams freigegebene Office-Dateien, eine in Teams gesendete Chat-Nachricht oder den Text eines in einem Teams-Kanal veröffentlichten Beitrags. Unser System erstellt eine eindeutige ID und verknüpft diese mit den Diagnosedaten des Benutzers. Wenn wir Diagnosedaten erhalten, die zeigen, dass die Teams-App 100 Mal abgestürzt ist, können wir mit dieser eindeutigen ID feststellen, ob es ein einzelner Benutzer war, der 100 Mal abgestürzt ist, oder ob es 100 verschiedene Benutzer waren, die jeweils einmal abgestürzt sind. Wir verwenden diese eindeutige ID nicht, um einen bestimmten Benutzer zu identifizieren.

Wenn Sie sehen möchten, welche Diagnosedaten an Microsoft gesendet werden, verwenden Sie den Diagnosedaten-Viewer, den Sie aus dem Microsoft Store kostenlos herunterladen und installieren können. Weitere Informationen finden Sie unter [Verwenden des Diagnosedaten-Viewers mit Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

> [!NOTE]
> Unterstützung zum Diagnosedaten-Viewer steht für Teams auf Geräten unter Android zur Verfügung. An Unterstützung für Teams auf Geräten unter Windows, macOS oder iOS wird zurzeit gearbeitet.

## <a name="required-service-data-for-connected-experiences"></a>Erforderliche Dienstdaten für verbundene Benutzeroberflächen

Bei den erforderliche Dienstdaten handelt es sich um Daten, mit denen wir diese cloudbasierten verbundenen Erfahrungen bereitstellen und dafür sorgen können, dass diese Erfahrungen sicher und wie erwartet funktionieren. Sie können sich dafür entscheiden, diese Funktionalität Ihren Benutzern nicht anzubieten. In diesem Fall werden diese Informationen Microsoft nicht zur Unterstützung verbundener Dienste zur Verfügung gestellt. Hier erfahren Sie mehr über [erforderliche Dienstdaten](/deployoffice/privacy/required-service-data).

## <a name="essential-services-for-microsoft-teams"></a>Grundlegende Dienste für Microsoft Teams

Es gibt auch eine Gruppe von Diensten, die für die Funktionsweise von Microsoft 365 Apps for Enterprise wesentlich sind und nicht deaktiviert werden können. Beispielsweise der Lizenzierungsdienst, der bestätigt, dass Sie über eine ordnungsgemäße Lizenz zur Verwendung von Microsoft 365 Apps for Enterprise verfügen. Erforderlicher Dienstdaten zu diesen Diensten werden erfasst und an Microsoft gesendet, unabhängig von anderen Richtlinieneinstellungen, die Sie konfiguriert haben.

Weitere Informationen finden Sie unter [Wesentliche Dienste für Office](/deployoffice/privacy/essential-services).