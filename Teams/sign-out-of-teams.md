---
title: Melden Sie sich von Microsoft Teams ab
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: Erfahren Sie, wie Sie sich von Microsoft Teams abmelden.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b11c58ced2ab089c181b28abe742ef8191452ea
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865674"
---
# <a name="sign-out-of-microsoft-teams"></a>Melden Sie sich von Microsoft Teams ab

Es wird empfohlen, dass Benutzer bei der Microsoft Teams-App angemeldet bleiben, um weiterhin Chats, eingehende Anrufe und andere Aktivitäten zu empfangen. Uns ist klar, dass Benutzer sich manchmal aus verschiedenen Gründen von Teams abmelden möchten:

- Weil sie mit Teams für den Tag fertig sind
- Sie möchten ein anderes Konto verwenden
- Weil sie ein Gerät verwenden, das sie mit einer anderen Person teilen

Aus diesen und anderen Gründen können Sie sich von der Teams-App abmelden und Ihre Sitzung beenden.

## <a name="account-sharing-between-apps"></a>Gemeinsame Nutzung von Konten zwischen Apps

Moderne Betriebssysteme ermöglichen die gemeinsame Nutzung von Konten zwischen verschiedenen Apps auf einem Gerät. Dieses Single Sign-On-Design (SSO) ermöglicht Benutzern die Verwendung mehrerer Apps auf ihrem Gerät, ohne dass sie sich bei jeder einzelnen App anmelden müssen. Teams steuert dieses Verhalten nicht, aber es nutzt die Vorteile, die dieses Design für die Benutzerfreundlichkeit bietet.

SSO hat einen wichtigen Einfluss auf die Abmeldung. Wenn sich Benutzer von Teams abmelden, werden die mit ihrem Konto verknüpften Daten aus der Teams-App entfernt. Andere Apps auf dem Gerät können jedoch weiterhin auf ihr Konto zugreifen. Dies bedeutet auch, dass Benutzer möglicherweise nicht aufgefordert werden, ihre Anmeldeinformationen erneut einzugeben, wenn sie sich mit demselben Konto wieder bei Teams anmelden.

## <a name="sign-out-of-teams-on-desktop"></a>Abmelden von Teams auf dem Desktop

Wenn Sie sich vom Teams-Desktopclient oder vom Browser abmelden möchten, wählen Sie oben in der App Ihr Profilbild und dann **Abmelden** aus.

Bei der Desktop-App können Sie auch mit der rechten Maustaste auf das App-Symbol in der Taskleiste klicken und dann **Abmelden** auswählen.

Wenn Sie mehrere Konten hinzugefügt haben, müssen Sie sich von jedem einzelnen Konto abmelden. Nachdem Sie sich von den Konten in Teams abgemeldet haben, müssen Sie Ihre Anmeldeinformationen möglicherweise beim nächsten Start der App erneut eingeben, um auf Ihr Konto zugreifen zu können.

## <a name="sign-out-of-teams-on-mobile-devices"></a>Abmelden von Teams auf mobilen Geräten

Auf einem mobilen Gerät können Sie sich von Teams abmelden, indem Sie zum Menü gehen, den Menüpunkt **Mehr** und dann **Abmelden** auswählen. Nach der Abmeldung, müssen Sie ihre Anmeldeinformationen erneut eingeben, wenn Sie die App das nächste Mal starten.

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>Globales An- und Abmelden für Mitarbeiter in Service und Produktion

Die Teams-Android-App unterstützt jetzt das globale An- und Abmelden, um Mitarbeitern in Service und Produktion eine einfache An- und Abmeldung zu ermöglichen. Ein Mitarbeiter kann ein Gerät aus dem Pool freigegebenen Geräte auswählen und es für die Dauer seiner Schicht mittels einmaliger Anmeldung „zu seinem machen“. Am Ende der Schicht sollte er sich global von dem Gerät abmelden können. Dadurch werden alle seine persönlichen Informationen und Unternehmensinformationen von dem Gerät entfernt, damit er es wieder zurück in den Gerätepool geben kann. Um diese Funktion nutzen zu können, muss sich das Gerät im Modus "Freigegeben" befinden. Wenn Sie erfahren möchten, wie ein freigegebenes Gerät eingerichtet wird, lesen Sie [Verwenden eines "Freigegeben"-Gerätemodus in Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

## <a name="manual-cleanup"></a>Manuelle Bereinigung

Es ist zwar selten, aber es ist möglich, dass Teams nach dem Abmelden keine vollständige Bereinigung durchführen kann. Basierend auf Benutzerberichten sind häufige Ursachen die Sperrung von Dateien durch einen Dienst, der auf dem System ausgeführt wird. Es kann aber auch andere Gründe geben, die von den jeweiligen Gerätekonfigurationen oder Richtlinien und Benutzerberechtigungen, die auf das Gerät angewendet werden, abhängig sind.

Ein dieses Problems zeigt sich häufige darin, dass Teams versucht, automatisch ein vorhandenes Konto auszuwählen, um den Benutzer zu anmelden. In solchen Fällen sollte der Benutzer den lokalen Cache von Teams manuell bereinigen. Weitere Informationen finden Sie unter [Anmelden oder Entfernen eines Kontos aus Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US).

## <a name="related-topics"></a>Verwandte Themen

[Anmelden oder Entfernen eines Kontos aus Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)