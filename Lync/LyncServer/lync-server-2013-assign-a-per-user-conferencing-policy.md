---
title: Zuweisen einer Konferenzrichtlinie auf Benutzerebene
TOCTitle: Zuweisen einer Konferenzrichtlinie auf Benutzerebene
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521015(v=OCS.15)
ms:contentKeyID: 49294390
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Konferenzrichtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die Konferenzrichtlinie ist eine der Einstellungen für ein Benutzerkonto, die Sie in der Lync Server-Systemsteuerung konfigurieren können.

Die Bereitstellung einer oder mehrerer Konferenzrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine globale Konferenzrichtlinie oder eine Konferenzrichtlinie auf Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer definiert wurde, werden automatisch die Konferenzbenutzerrechte und -berechtigungen in der globalen Konferenzrichtlinie verwendet.

Nach Erstellung mindestens einer Konferenzrichtlinie auf Benutzerebene führen Sie die Schritte in diesem Thema aus, um die Richtlinie mit den Benutzerrechten und -berechtigungen zuzuweisen, die der Server den von einem bestimmten Benutzer organisierten Besprechungen erteilen soll.

Eine Liste aller verfügbaren Konferenzrichtlinieneinstellungen finden Sie unter [Referenz zu den Konferenzrichtlinieneinstellungen](lync-server-2013-conferencing-policy-settings-reference.md).

Ausführliche Informationen zum Erstellen von Konferenzrichtlinien finden Sie unter [Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## So weisen Sie eine Konferenzrichtlinie auf Benutzerebene zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
      - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
    4.  Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.
        

        > [!TIP]
        > Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.

    
    5.  Klicken Sie auf **Suchen**.

6.  Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.
    

    > [!TIP]
    > Wenn Sie dieselbe Benutzerkonferenzrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Konferenzrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]
    > Da Sie im Dialogfeld <STRONG>Richtlinien zuweisen</STRONG> mehrere Richtlinien konfigurieren können, wird die Option <STRONG>&lt;Beibehalten&gt;</STRONG> für alle Richtlinien im Dialogfeld standardmäßig aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Wählen Sie **\<Automatisch\>**, um eine automatische Auswahl der globalen Richtlinie oder, falls definiert, der Richtlinie auf Standortebene durch Lync Server 2013 zuzulassen.
    
      - Klicken Sie auf der Seite **Konferenzrichtlinie** auf den Namen einer Konferenzrichtlinie auf Benutzerebene, die Sie zuvor definiert haben.
        

        > [!TIP]
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## Zuweisen einer Konferenzrichtlinie auf Benutzerebene mithilfe der Lync Server PowerShell-Cmdlets

Konferenzrichtlinien auf Benutzerebene können außerdem über die Lync Server PowerShell und das Grant-CsConferencingPolicy-Cmdlet zugewiesen werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Zuweisen einer Konferenzrichtlinie auf Benutzerebene für einen einzelnen Benutzer

  - Der folgende Befehl weist dem Benutzer Ken Myer die Konferenzrichtlinie „RedmondConferencingPolicy“ auf Benutzerebene zu.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## Zuweisen einer Konferenzrichtlinie auf Benutzerebene für verschiedene Benutzer

  - Dieser Befehl weist die Konferenzrichtlinie „HRConferencingPolicy“ auf Benutzerebene allen Benutzern zu, die in der Personalabteilung tätig sind. Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation zum [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlet.
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## Aufheben der Zuweisung einer Konferenzrichtlinie auf Benutzerebene

  - Mit dem folgenden Befehl wird die Zuweisung sämtlicher Konferenzrichtlinien, die dem Benutzer Ken Myer zuvor zugeordnet wurden, aufgehoben. Nach der Aufhebung der Konferenzrichtlinie auf Benutzerebene wird Ken Myer automatisch unter Verwendung der globalen Richtlinie bzw. (sofern vorhanden) von der Richtlinie seines lokalen Standorts verwaltet. Die Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy)-Cmdlet.

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  

#### Weitere Ressourcen

[Zuweisen von Richtlinien auf Benutzerebene](lync-server-2013-assigning-per-user-policies.md)

