---
title: Einrichten der Lizenz für Telefone für gemeinsame Bereiche für Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Hier erfahren Sie, wie Sie Telefone in öffentlichen Bereichen für Lobbys, Empfangsbereichen und Konferenzräume einrichten '
ms.openlocfilehash: b7fb997a8e9367c4a3b8629f037ad79871b64b25
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2019
ms.locfileid: "30121044"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Einrichten der Lizenz für Telefone für gemeinsame Bereiche für Microsoft Teams

Ein Telefon im öffentlichen Bereich wird in der Regel platziert, in einen Bereich wie eine Lobby oder einem anderen Bereich, der So rufen an viele Personen zur Verfügung steht. beispielsweise ein Empfang Bereich, Wartebereich oder Konferenz Telefon. Telefone in öffentlichen Bereichen Geräte, sondern als Benutzer eingerichtet sind, und in einem Netzwerk automatisch anmelden können.

In den folgenden Schritten helfen wir Ihnen das Einrichten eines Kontos für Telefonsystem Telefone in öffentlichen Bereichen für Ihre Organisation bereitstellen. Für eine genauere Besprechungsraum wünschen, Audiokonferenzen, einschließlich die dedizierte Besprechungsraum Lizenz mit einer Besprechung Mitgliederlisten Raum Gerät. 

Zunächst müssen Sie lediglich sind Purchase eine Lizenz Common Area Phone (CAP) und stellen Sie sicher, dass Sie ein zertifiziertes Telefon verfügen. Zum Suchen nach und erfahren mehr über zertifizierten Telefone, wechseln Sie zur [Microsoft-Teams, Geräte](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen

1. Wechseln Sie in das Office 365 Administrationscenter zu **Abrechnung** > **Dienste erwerben** und erweitern Sie dann **andere Pläne**.

    ![Screenshot, der zeigt der Kachel "Common Area Phone"](media/set-up-common-area-phone-image1.png)

2. Wählen Sie **Telefone in öffentlichen Bereichen** > **Jetzt kaufen**.

3. Klicken Sie auf der Seite **Auschecken** auf **Jetzt kaufen**.

4. Erweitern Sie **Add-on-Abonnements** , und klicken Sie dann auf Kaufen aufrufen planen. Wählen Sie die **nationalen Plan aufrufen** oder **nationalen und internationalen aufrufen planen**.

> [!NOTE]
> Sie benötigen für das Telefonsystem keine Lizenz. Sie ist in der Lizenz Telefon für gemeinsame Bereiche enthalten.

Weitere Informationen zu Lizenzen finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen

1. Wechseln Sie in das Office 365 Administrationscenter zu **Benutzern** > **aktive Benutzer** > **Hinzufügen eines Benutzers**.

2. Geben Sie einen Benutzernamen wie "Main" für den ersten Namen und "Empfang" für den zweiten Namen.

3. Geben Sie einen Anzeigenamen ein, wenn dies nicht der Fall einer standardbrowserformulare wie "Main Empfang".

4. Geben Sie einen Benutzernamen ein, wie "MainReception" oder "Mainlobby."

5. Für Telefone in öffentlichen Bereichen möchten Sie möglicherweise manuell festlegen eines Kennworts oder über das gleiche Kennwort für alle Ihre Telefone in öffentlichen Bereichen. Darüber hinaus glauben Sie zum Deaktivieren des Kontrollkästchens **stellen diesen Benutzer ändern ihres Kennworts beim erstmaligen Anmelden** .

6. Dem Benutzer die Lizenzen zuweisen. Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern. Aktivieren Sie das Telefon im öffentlichen Bereich, und wählen Sie entweder einen **Nationalen aufrufen planen** oder eine **in- und International aufrufen planen**. 

    ![Screenshot mit lizenzzuweisung](media/set-up-common-area-phone-image2.png)

Weitere Informationen finden Sie unter [Benutzer hinzufügen](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen

Verwenden Sie die Skype für Business Administrationscenter, eine Nummer, die dem Benutzer zuzuweisen.

1. Wählen Sie in der Microsoft-365-Verwaltungskonsole **Admin zentriert** > **Teams & Skype** > **Legacy-Portal**.

2. Wählen Sie in der Skype für Business Administrationscenter, **Stimme** > **Rufnummern**.

3.  Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.

4. Geben Sie auf der Seite **zuweisen** im Feld Benutzername den VoIP den Namen des Benutzers, der das Telefon, und wählen Sie dann den Benutzer in der Dropdownliste **Wählen Sie einen VoIP-Benutzer** verwendet werden soll.

5. Hier müssen Sie eine Notfalladresse angeben. Wählen Sie aus der Dropdown-Liste **Suchen nach Stadt**, **Suchen nach Beschreibung**, oder **Suchen Sie nach Standort** , und geben Sie die Stadt, Beschreibung oder Speicherort in das Textfeld. Sobald Sie suchen, suchen Sie unter **Wählen Sie Notfall Adresse** für das richtige für Sie auswählen.

6. Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:

   ![Screenshot mit lizenzzuweisung](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Benutzer werden nur angezeigt, wenn sie eine Telefonsystem Lizenz angewendet haben. Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.

Weitere Informationen finden Sie unter [Getting Rufnummern für Ihre Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).

Sie können auch Ihre Telefonnummer schalten, indem Sie mit einem anderen Netzbetreiber und "Port" oder zu Office 365 übertragen. Finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).


