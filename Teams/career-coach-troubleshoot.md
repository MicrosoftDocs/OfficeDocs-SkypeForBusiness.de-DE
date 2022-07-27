---
title: Problembehandlung beim Karrierecoach für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie häufige Probleme im Career Coach für Microsoft Teams behandeln.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024170"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Problembehandlung beim Karrierecoach für Microsoft Teams

Dieser Artikel richtet sich an IT-Administratoren im Hochschulbereich, die Probleme mit Career Coach für Microsoft Teams beheben müssen.

Im Folgenden finden Sie die allgemeinen Probleme und Lösungsschritte, die IT-Administratoren mit Career Coach unternehmen können.

## <a name="missing-required-configuration-data"></a>Fehlende erforderliche Konfigurationsdaten

Wenn in der Career Coach-Erfahrung "Career Coach ist zurzeit so eingerichtet, dass Sie es bald verwenden können" angezeigt wird, **wurden nicht alle erforderlichen Konfigurationsdaten hinzugefügt**.

Die folgenden **Abschnitte müssen abgeschlossen sein** , bevor Career Coach verwendet werden kann:

- [Marke und Präferenzen](career-coach-set-up-steps.md#brand-and-preferences)
- [LinkedIn-Verbindung](career-coach-set-up-steps.md#linkedin-connection)
- [Kurskatalog](career-coach-set-up-steps.md#course-catalog)
- [Studiengebiete](career-coach-set-up-steps.md#fields-of-study)

Verweisen Sie auf den [Konfigurationsstatus des Karrierecoachs](career-coach-set-up-steps.md#configuration-status) , um zu sehen, welche Einstellungen abgeschlossen werden müssen.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>Falsche Formatierung des Kurskatalogs oder der Studienfelder

CsVs für Kurskatalog und Studienfeld haben erforderliche Formate und eine maximale Größe von 18 MB.

Verweisen Sie auf das [Career Coach-Kurskatalog-Dokumentschema](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) und [die Career Coach-Felder des Studiendokumentschemas](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) , um eine ordnungsgemäße Konfiguration sicherzustellen.

Außerdem sollte eine Kurskatalogdatei nicht mehr als 15.000 Zeilen enthalten, um eine erfolgreiche Verarbeitung sicherzustellen.

## <a name="missing-fields-in-career-coach-settings-pages"></a>Fehlende Felder auf den Einstellungsseiten des Karrierecoachs

Die Einstellungsseiten des Karrierecoachs verfügen über erforderliche Felder. Wenn die erforderlichen Felder nicht ausgefüllt werden, wird die Seite nicht übermittelt.

Möglicherweise wird keine Warnmeldung angezeigt, und die Seite wird nicht übermittelt.

Die Übermittlung ist erfolgreich, wenn oben auf der Seite ein grünes Banner angezeigt wird.

## <a name="setup-policy-changes-arent-complete"></a>Setuprichtlinienänderungen sind nicht abgeschlossen.

Wenn Career Coach in Microsoft Teams für Benutzer nicht angezeigt wird, sind die Setuprichtlinienänderungen möglicherweise noch nicht wirksam. Career Coach wird für Benutzer in Microsoft Teams erst installiert und angeheftet, wenn die Setuprichtlinienänderungen wirksam werden. Es kann einige Stunden dauern, bis Richtlinienänderungen wirksam werden.

Career Coach kann jedoch direkt aus dem Microsoft Teams App Store installiert werden.

- Wenn Benutzer karrierecoach im Microsoft Teams App Store nicht finden können, überprüfen Sie Ihre App-Berechtigungsrichtlinien, und stellen Sie sicher, dass Career Coach keine blockierte App ist.
- Career Coach ist eine Microsoft-App, und es ist eine bewährte Methode, Microsoft-Apps nach Berechtigungsrichtlinien zuzulassen. Weitere Informationen zum [Konfigurieren von Berechtigungsrichtlinien](teams-app-permission-policies.md).

## <a name="career-coach-initialization-isnt-complete"></a>Die Initialisierung des Karrierecoachs ist noch nicht abgeschlossen

Möglicherweise tritt die folgende Fehlermeldung auf: "Wir können die App-Einstellungen nicht abrufen. Versuchen Sie es erneut. Wenn Weiterhin Probleme auftreten, wenden Sie sich an den Microsoft-Kundensupport."

Überprüfen Sie den **Dienstbereitstellungsstatus** auf der [Einstellungsseite des Karrierecoachs](career-coach-set-up-steps.md#career-coach-settings-status).

Wenn Ihr Mandant noch initialisiert wird, warten Sie 15 Minuten, und versuchen Sie es erneut. Öffnen Sie ein Supportticket, wenn Sie den Fehler weiterhin erhalten.
