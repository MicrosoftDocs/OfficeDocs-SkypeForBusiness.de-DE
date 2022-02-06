---
title: Erstellen von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server erstellen.'
---

# <a name="create-conferencing-policies-in-skype-for-business-server"></a>Erstellen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server erstellen.
  
Sie können Konferenzrichtlinien mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell erstellen.
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Erstellen von Konferenzrichtlinien mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen**" und dann auf **"Konferenzrichtlinie**".
    
4. Klicken Sie auf **Neu**, und führen Sie eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue Konferenzrichtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.
    
   - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
     > [!NOTE]
     > Der Standortname wird zum Konferenzrichtliniennamen. sie kann nicht geändert werden. 
  
5. Geben Sie in **Beschreibung** eine Beschreibung für die Richtlinie ein.
    
6. Geben Sie unter **Organisatorrichtlinie** in **Maximaler Besprechungsumfang** die Höchstzahl an Benutzern ein, die für eine Besprechung zugelassen werden sollen. Der maximale Besprechungsumfang ist standardmäßig auf 250 festgelegt.
    
7. Um Benutzer daran zu hindern, anonyme Benutzer zu Besprechungen einzuladen, deaktivieren Sie das Kontrollkästchen **Teilnehmern das Einladen anonymer Benutzer gestatten**. Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation haben und daher nicht authentifiziert sind. In der Standardeinstellung können Benutzer anonyme Benutzer zu Besprechungen einladen.
    
8. Führen Sie im Abschnitt **Aufzeichnung** eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Keine**, um Teilnehmer an der Aufzeichnung von Besprechungen zu hindern. Dies ist die Standardeinstellung.
    
   - Klicken Sie auf **Aufzeichnung aktivieren**, um Teilnehmern die Aufzeichnung von Besprechungen zu gestatten.
    
9. Um externen Teilnehmern das Aufzeichnen von Besprechungen zu erlauben, aktivieren Sie das Kontrollkästchen **Aufzeichnung durch Partnerteilnehmer und anonyme Teilnehmer zulassen**. In der Standardeinstellung werden externe Teilnehmer an der Aufzeichnung von Besprechungen gehindert.
    
10. Führen Sie im Abschnitt **Audio/Video** eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **Keine**, um die Verwendung von Audio und Video zu verhindern.
    
    - Klicken Sie auf **IP-Audio aktivieren**, um die Verwendung von Audio, nicht jedoch von Video zuzulassen.
    
    - Klicken Sie auf **IP-Audio/Video aktivieren**, um die Verwendung von Audio und Video zuzulassen. Dies ist die Standardeinstellung.
    
11. Wenn Sie die Verwendung von Audio im Abschnitt **Audio/Video** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
    - Wenn Sie Benutzer daran hindern möchten, per Einwahl an einer Besprechung teilzunehmen, deaktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
    - Wenn Sie Benutzern die Einwahl in Besprechungen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an Besprechungen über eine ausgehende Telefonverbindung erlauben möchten, aktivieren Sie das Kontrollkästchen **Ausgehende Verbindung durch anonyme Teilnehmer zulassen**. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Besprechung teilzunehmen. In der Standardeinstellung können anonyme Benutzer nicht über ausgehende Telefonverbindungen an Besprechungen teilnehmen.
    
12. Wenn Sie die Verwendung von Videos in **Audio/Video** zugelassen haben, aktivieren Sie **die Option "Mehrere Videostreams zulassen**".
    
13. Führen Sie im Abschnitt **Datenzusammenarbeit** eine der folgenden Aktionen aus:
    
    - Wenn Sie keine Datenzusammenarbeit zulassen möchten, klicken Sie auf **Keine**.
    
    - Zum Zulassen einer Datenzusammenarbeit klicken Sie auf **Datenzusammenarbeit aktivieren**. Dies ist die Standardeinstellung.
    
14. Wenn Sie die Datenzusammenarbeit im Abschnitt **Datenzusammenarbeit** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
    - Deaktivieren Sie das Kontrollkästchen **Download von Inhalten durch Partnerteilnehmer und anonyme Teilnehmer zulassen**. In der Standardeinstellung können externe Benutzer Inhalte herunterladen.
    
    - Deaktivieren Sie das Kontrollkästchen **Übertragen von Dateien durch Teilnehmer zulassen**, um Dateiübertragungen zu verhindern. In der Standardeinstellung können Dateien übertragen werden.
    
    - Deaktivieren Sie das Kontrollkästchen **Anmerkungen aktivieren**, um die Verwendung von Anmerkungen zu verhindern. Wenn Sie Anmerkungen in freigegebenen PowerPoint Präsentationen verwenden möchten, deaktivieren **Sie die Option zum Aktivieren PowerPoint Anmerkungen**. In der Standardeinstellung sind Anmerkungen zulässig.
    
    - Deaktivieren Sie das Kontrollkästchen **Abstimmungen aktivieren**, um die Verwendung von Abstimmungen zu verhindern. In der Standardeinstellung sind Abstimmungen zulässig.
    
15. Führen Sie im Abschnitt **Anwendungsfreigabe** eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **Anwendungsfreigabe deaktivieren**, um die Verwendung der Anwendungsfreigabe zu verhindern.
    
    - Klicken Sie auf **Anwendungsfreigabe aktivieren**, um die Verwendung der Anwendungsfreigabe zuzulassen. Dies ist die Standardeinstellung.
    
16. Wenn Sie die Anwendungsfreigabe im Abschnitt **Anwendungsfreigabe** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
    - Deaktivieren Sie das Kontrollkästchen **Übernahme der Steuerung durch Teilnehmer zulassen**, um Teilnehmer an der Übernahme der Steuerung für die Anwendungsfreigabe zu hindern. In der Standardeinstellung können Teilnehmer die Steuerung für die Anwendungsfreigabe übernehmen.
    
    - Wenn Sie Besprechungsteilnehmern die Übernahme der Steuerung für die Anwendungsfreigabe ermöglichen möchten, aktivieren Sie das Kontrollkästchen **Steuerungsübernahme durch Partnerteilnehmer und anonyme Teilnehmer zulassen**, um externen Benutzern die Übernahme der Steuerung für die Anwendungsfreigabe zu erlauben. In der Standardeinstellung können externe Benutzer die Steuerung für die Anwendungsfreigabe nicht übernehmen.
    
17. Führen Sie unter **Teilnehmerrichtlinie** eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **Anwendungs- und Desktopfreigabe deaktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zu verhindern.
    
    - Klicken Sie auf **Anwendungsfreigabe aktivieren**, um eine Anwendungsfreigabe, nicht jedoch die Freigabe des Desktops zu ermöglichen.
    
    - Klicken Sie auf **Anwendungs- und Desktopfreigabe aktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zuzulassen. Dies ist die Standardeinstellung.
    
18. Deaktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Dateiübertragung aktivieren**, um Peer-zu-Peer-Dateiübertragungen zu verhindern. In der Standardeinstellung sind Peer-zu-Peer-Dateiübertragungen zulässig.
    
19. Aktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Aufzeichnung aktivieren**, um eine Peer-zu-Peer-Aufzeichnung zuzulassen. In der Standardeinstellung sind Peer-zu-Peer-Aufzeichnungen unzulässig.
    
20. Aktivieren Sie das Kontrollkästchen **Teilnahme mit mehreren Videostreams aktivieren**, um die Teilnahme mit mehreren Videostreams zuzulassen. In der Standardeinstellung sind mehrere Videostreams zulässig.
    
21. Klicken Sie auf **Commit ausführen**.
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Erstellen von Konferenzrichtlinien mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Erstellen von Konferenzrichtlinien das Cmdlet **"New-CsConferencingPolicy** ".
  
Im folgenden Beispiel wird eine neue Konferenzrichtlinie mit der Identity SalesConferencingPolicy erstellt. Diese Richtlinie verwendet alle Standardwerte für eine Konferenzrichtlinie mit Ausnahme einer: MaxMeetingSize. In diesem Beispiel wird die maximale Größe für eine Besprechung auf 50 anstelle des Standardwerts von 250 festgelegt:
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

Weitere Informationen, einschließlich einer vollständigen Syntaxbeschreibung und einer Liste von Parametern, finden Sie unter [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).
