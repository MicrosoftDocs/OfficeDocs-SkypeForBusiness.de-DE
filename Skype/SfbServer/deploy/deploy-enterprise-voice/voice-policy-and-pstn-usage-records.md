---
title: Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Zusammenfassung: Erstellen Sie oder ändern Sie der VoIP-Richtlinien und konfigurieren Sie PSTN-verwendungsdatensätzen mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: c1fb142718008bd2a53582a3952bd9b0b9477ca6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888241"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen

**Zusammenfassung:** Erstellen Sie oder ändern Sie der VoIP-Richtlinien und konfigurieren Sie PSTN-verwendungsdatensätzen mithilfe der Skype für Business Server-Systemsteuerung.

> [!NOTE]
> Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag zugeordnet sein. Finden eine Liste aller PSTN-verwendungsdatensätzen in Ihrer Bereitstellung von Enterprise-VoIP verfügbar und deren Eigenschaften anzeigen, finden Sie unter [View PSTN-Verwendungseinträge in Skype für Unternehmen](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>So erstellen Sie eine VoIP-Richtlinie

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Richtlinie**.

3. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Neu** und wählen Sie einen Bereich für die neue Richtlinie:

   - Eine **Standortrichtlinie** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einer Benutzerrichtlinie zugeordnet wurden. Wenn Sie eine Richtlinie auf Standortebene erstellen möchten, wählen Sie den gewünschten Standort im Dialogfeld **Standort auswählen**. Wenn bereits eine VoIP-Richtlinie für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.

   - Eine **Benutzerrichtlinie** kann auf bestimmte Benutzer oder Gruppen angewendet werden.

4. Wenn Sie eine VoIP-Richtlinie auf Benutzerebene erstellen, geben Sie im Feld **Name** einen beschreibenden Namen für die Richtlinie ein.

    > [!NOTE]
    > Bei Erstellung einer VoIP-Richtlinie auf Standortebene wird das Feld **Name** unter **Neue VoIP-Richtlinie** mit dem Standortnamen vorausgefüllt und kann nicht geändert werden.

5. (Optional) Geben Sie zusätzliche beschreibende Informationen zur VoIP-Richtlinie ein.

6. Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die **Anruffunktionen** für diese VoIP-Richtlinie zu aktivieren oder zu deaktivieren:

   - **Des Wechsels der Voicemail** verhindert, dass Anrufe von wird sofort an des Benutzers Mobiltelefon Voicemail-System weitergeleitet, wenn Gleichzeitiges Klingeln konfiguriert ist und das Telefon aus, nicht genügend Batterie oder außerhalb des gültigen Bereichs aktiviert ist.

    > [!NOTE]
    > Dieses Feature ist nur über die Skype für Business Server-Verwaltungsshell konfigurierbar

   - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Skype für Business Server bietet einen deutlich größeren Bereich von Konfigurationsoptionen für die anrufweiterleitung. Wenn z. B. eine Organisation nicht möchte, dass eingehende Anrufe extern an das Festnetz (Public Switched Telephone Network, PSTN) weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie anwenden, um diese Einschränkungen durchzusetzen. Diese Option ist standardmäßig aktiviert.

   - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In Skype für Business Server kann eine Stellvertretung konfigurieren, Gleichzeitiges Klingeln, mit dem können eingehende Anrufe an seinem Manager alle Gleichzeitiges Klingeln Ziele der Stellvertretung angeboten werden soll. Dadurch wird die Stellvertretung flexibler reagieren Aufrufe an den Manager weitergeleitet. Diese Option ist standardmäßig aktiviert.

   - **Anrufdurchstellung** ermöglicht Benutzern, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

   - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

   - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Skype für Business Server bietet einen deutlich größeren Bereich von Konfigurationsoptionen für Gleichzeitiges Klingeln. Diese Option ist standardmäßig aktiviert.

   - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

   - **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Nutzern, denen diese Richtlinie zugewiesen wurde, an andere Nutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

   - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.

    > [!NOTE]
    > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet und für angemessene Entscheidungen der Anrufsteuerung reserviert werden.

   - **Nachverfolgung von Missbrauch durch Anrufer** ermöglicht Nutzern das Melden von Drohanrufen (z. B. Bombendrohungen) über die Clientbenutzeroberfläche. Die Anrufe werden anschließend in den Kommunikationsdatensätzen (KDS) gekennzeichnet. Diese Option ist standardmäßig deaktiviert.

   - **Beschäftigt-Optionen** aktiviert oder deaktiviert Beschäftigt-Optionen für die angegebene VoIP-Richtlinie. Mit Beschäftigt-Optionen können eingehende Anrufe an die Voicemail weitergeleitet oder mit einem Besetztzeichen abgelehnt werden, wenn der Zielbenutzer des Anrufs am Telefon ist. Bei Beschäftigt-Optionen handelt es sich um eine neue im kumulativen Update für Juli 2016 eingeführte VoIP-Richtlinie. Bei Aktivierung dieses Parameters werden Beschäftigt-Optionen aktiviert, bei Deaktivierung werden diese Optionen deaktiviert. Weitere Informationen finden Sie unter [Planen für Skype für Business Server ausgelastet Optionen](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) und [Installieren und Konfigurieren von beschäftigt Optionen für Skype für Business Server](install-and-configure-busy-options.md).

7. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste aller PSTN-Verwendungseinträge auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Einträge, die Sie dieser VoIP-Richtlinie zuordnen möchten und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus der VoIP-Richtlinie zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser VoIP-Richtlinie zuzuordnen:

    a. Klicken Sie auf **Neu**.

    b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein. Sie möchten beispielsweise ein PSTN-Verwendung Datensatz NamedRedmond für Vollzeitmitarbeiter befindet sich in Redmond und einem anderen NamedRedmondTemps für temporäre Mitarbeiter zu erstellen.

    > [!NOTE]
    > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld **Name** nicht mehr bearbeitet werden.

    c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

   - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

    d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

    a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten und klicken Sie auf **Details einblenden**.

    b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

   - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

    c. Klicken Sie auf **OK**.

8. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um einen Datensatz Position in der Liste zu ändern, markieren Sie den Namen des Datensatzes, und klicken Sie auf den Pfeil nach oben oder nach-unten Sie-Pfeil.

    > [!IMPORTANT]
    > Die Reihenfolge, in welche, die PSTN-verwendungsdatensätzen, in der VoIP-Richtlinie aufgeführt sind, ist relevant. Skype für Business Server durchläuft die Liste von oben nach unten. Es wird empfohlen, dass Sie die Liste beispielsweise nach der Häufigkeit der Verwendung, organisieren: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für die Anrufweiterleitung und das gleichzeitige Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Um dieselben PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie in dieser VoIP-Richtlinie zu verwenden, wählen Sie aus dem Dropdownmenü die Option **Mithilfe der PSTN-Anrufverwendung weiterleiten** aus.

   - Wenn die anrufweiterleitung und Gleichzeitiges Klingeln zu internen Skype für Unternehmensbenutzer nur zulassen möchten, wählen Sie die Option **Route zu internen Skype für Unternehmensbenutzer nur** aus dem Dropdown-Menü. Anrufe werden nicht an externe PSTN-Nummern weitergeleitet.

   - Um andere PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie für diese VoIP-Richtlinie anzugeben, wählen Sie aus dem Dropdownmenü die Option **Mithilfe benutzerdefinierter PSTN-Verwendung weiterleiten** aus. Mit dieser Option wird ein Steuerelement angezeigt, um vorhandene PSTN-Verwendungseinträge auszuwählen oder um neue PSTN-Verwendungseinträge speziell für die Anrufweiterleitung und für das gleichzeitige Klingeln zu erstellen.

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuzuordnen:

    a. Klicken Sie auf **Neu**.

    b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.

    > [!NOTE]
    > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld **Name** nicht mehr bearbeitet werden.

    c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

   - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

    d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

    a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten und klicken Sie auf **Details einblenden**.

    b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

   - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

    c. Klicken Sie auf **OK**.

10. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Übersetzte Nummer zum Testen** angezeigt.

11. Klicken Sie auf **OK**.

12. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit ausführen** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.

13. (Optional) Voicemail Escape erkennt, dass ein Anruf wurde durch den Benutzer Mobiltelefon Voicemail sofort beantwortet, und den Anruf an die Voicemail Mobiltelefon trennt. Dadurch wird den Anruf an weiterhin Anrufen auf den Benutzer des anderen Endpunkten, mit dem dem Benutzer die Möglichkeit, den Anruf entgegenzunehmen. Weitere Informationen zum Konfigurieren einer Richtlinie für Voicemail finden Sie unter [Konfigurieren des Wechsels der Voicemail in Skype für Unternehmen](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>So ändern Sie eine VoIP-Richtlinie

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und anschließend auf **VoIP-Richtlinie**.

3. Doppelklicken Sie auf der Seite **VoIP-Richtlinie** auf den Namen einer VoIP-Richtlinie.

    > [!NOTE]
    > Der Bereich und der Name wurden bei Erstellung der VoIP-Richtlinie festgelegt. Sie können nicht geändert werden.

4. (Optional) Geben Sie in **VoIP-Richtlinie bearbeiten** zusätzliche Informationen zur Beschreibung der VoIP-Richtlinie ein.

5. Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die einzelnen **Anruffunktionen** zu aktivieren bzw. zu deaktivieren:

   - **Des Wechsels der Voicemail** verhindert, dass Anrufe von wird sofort an des Benutzers Mobiltelefon Voicemail-System weitergeleitet, wenn Gleichzeitiges Klingeln konfiguriert ist und das Telefon aus, nicht genügend Batterie oder außerhalb des gültigen Bereichs aktiviert ist.

    > [!NOTE]
    > Dieses Feature ist nur über die Skype für Business Server-Verwaltungsshell konfigurierbar

   - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Skype für Business Server bietet einen deutlich größeren Bereich von Konfigurationsoptionen für die anrufweiterleitung. Wenn z. B. eine Organisation nicht möchte, dass eingehende Anrufe extern an das Festnetz (Public Switched Telephone Network, PSTN) weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie anwenden, um diese Einschränkungen durchzusetzen. Diese Option ist standardmäßig aktiviert.

   - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In Skype für Business Server kann eine Stellvertretung konfigurieren, Gleichzeitiges Klingeln, mit dem können eingehende Anrufe an seinem Manager alle Gleichzeitiges Klingeln Ziele der Stellvertretung angeboten werden soll. Dadurch wird die Stellvertretung flexibler reagieren Aufrufe an den Manager weitergeleitet. Diese Option ist standardmäßig aktiviert.

   - **Anrufdurchstellung** ermöglicht Benutzern, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

   - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

   - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Skype für Business Server bietet einen deutlich größeren Bereich von Konfigurationsoptionen für Gleichzeitiges Klingeln. Diese Option ist standardmäßig aktiviert.

   - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

   - **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Nutzern, denen diese Richtlinie zugewiesen wurde, an andere Nutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

   - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Nutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.

     > [!NOTE]
     > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet werden.

   - **Nachverfolgung bei Missbrauch durch Anrufer** ermöglicht Nutzern das Melden von Drohanrufen (z. B. Bombendrohungen) über die Clientbenutzeroberfläche, wo die Anrufe anschließend in den Kommunikationsdatensätzen (KDS) gekennzeichnet werden. Diese Option ist standardmäßig deaktiviert.

6. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste aller PSTN-Verwendungseinträge auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Einträge, die Sie dieser VoIP-Richtlinie zuordnen möchten und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus der VoIP-Richtlinie zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser VoIP-Richtlinie zuzuordnen:

    a. Klicken Sie auf **Neu**.

    b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein. Sie möchten beispielsweise ein PSTN-Verwendung Datensatz NamedRedmond für Vollzeitmitarbeiter befindet sich in Redmond und einem anderen Datensatz NamedRedmondTemps für temporäre Mitarbeiter zu erstellen.

    > [!NOTE]
    > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld **Name** nicht mehr bearbeitet werden.

    c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

   - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

    d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

    a. Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten und klicken Sie auf **Details anzeigen**.

    b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

   - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

    c. Klicken Sie auf **OK**.

7. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um einen Datensatz Position in der Liste zu ändern, markieren Sie den Namen des Datensatzes, und klicken Sie auf den Pfeil nach oben oder nach-unten Sie-Pfeil.

    > [!NOTE]
    > Die Reihenfolge, in welche, die PSTN-verwendungsdatensätzen, in der VoIP-Richtlinie aufgeführt sind, ist relevant. Skype für Business Server durchläuft die Liste von oben nach unten. Es wird empfohlen, dass Sie die Liste beispielsweise nach der Häufigkeit der Verwendung, organisieren: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für die Anrufweiterleitung und das gleichzeitige Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Um dieselben PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie in dieser VoIP-Richtlinie zu verwenden, wählen Sie aus dem Dropdownmenü die Option **Mithilfe der PSTN-Anrufverwendung weiterleiten** aus.

   - Um die anrufweiterleitung und Gleichzeitiges Klingeln zu internen Skype Business nur für Benutzer zu ermöglichen, wählen Sie aus dem Dropdown-Menü **Route zu internen Skype für Unternehmensbenutzer nur** aus. Die Anrufe werden dann nicht an externe PSTN-Nummern weitergeleitet.

   - Um andere PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden, als die für diese VoIP-Richtlinie verwendeten, wählen Sie die Option **Mithilfe benutzerdefinierter PSTN-Verwendungen weiterleiten** im Dropdownmenü aus. Bei Auswahl dieser Option wird ein Steuerelement angezeigt, über das vorhandene PSTN-Verwendungsdatensätze ausgewählt oder neue PSTN-Verwendungsdatensätze erstellt werden können, die speziell auf die Anrufweiterleitung und gleichzeitiges Klingeln ausgerichtet sind.

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuzuordnen:

    a. Klicken Sie auf **Neu**.

    b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.

    > [!NOTE]
    > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld **Name** nicht mehr bearbeitet werden.

    c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

   - Markieren Sie die Route und klicken Sie anschließend auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Weitere Informationen hierzu finden Sie unter [Ändern einer VoIP-Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

    d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten und klicken Sie auf **Details anzeigen**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

     - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.

     - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

     - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Weitere Informationen hierzu finden Sie unter [Ändern einer VoIP-Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     c. Klicken Sie auf **OK**.

9. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Übersetzte Nummer zum Testen** angezeigt.

10. Klicken Sie auf **OK**.

11. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit ausführen** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.

12. (Optional) Voicemail Escape erkennt, dass ein Anruf wurde durch den Benutzer Mobiltelefon Voicemail sofort beantwortet, und den Anruf an die Voicemail Mobiltelefon trennt. Dadurch wird den Anruf an weiterhin Anrufen auf den Benutzer des anderen Endpunkten, mit dem dem Benutzer die Möglichkeit, den Anruf entgegenzunehmen. Ausführliche Informationen zum Konfigurieren einer Richtlinie für Voicemail finden Sie unter [Konfigurieren des Wechsels der Voicemail in Skype für Unternehmen](configure-voice-mail-escape.md).

## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Verwendungseinträge in Skype für Unternehmen](view-pstn-usage-records.md)

[Erstellen oder Ändern einer VoIP-Route in Skype für Unternehmen](create-or-modify-a-voice-route.md)

[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md)

[Konfigurieren des Wechsels der Voicemail in Skype für Unternehmen](configure-voice-mail-escape.md)

