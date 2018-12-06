---
title: Zuweisen einer Clientversionsrichtlinie auf Benutzerebene
TOCTitle: Zuweisen einer Clientversionsrichtlinie auf Benutzerebene
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182607(v=OCS.15)
ms:contentKeyID: 49295947
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Clientversionsrichtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die Clientversionsrichtlinie ist eine der Einstellungen für ein Benutzerkonto, die Sie in der Lync Server-Systemsteuerung konfigurieren können.

Die Bereitstellung einer oder mehrerer Clientversionsrichtlinien auf Benutzerebene ist optional. Sie können auch lediglich eine globale Clientversionsrichtlinie bzw. Clientversionsrichtlinien auf Standort- oder Poolebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine bestimmte Richtlinie auf Standort-, Pool- oder Benutzerebene zugewiesen ist, können sich standardmäßig alle Clients für Lync Server 2013 registrieren, die in der globalen Clientversionsrichtlinie definiert sind.

Nachdem Sie mindestens eine Clientversionsrichtlinie auf Benutzerebene erstellt haben, weisen Sie sie mithilfe der Verfahren in diesem Thema die Richtlinie zur Angabe der Clientversionen zu, die sich für Lync Server registrieren dürfen.

Ausführliche Informationen zum Erstellen von Clientversionsrichtlinien auf Benutzerebene finden Sie unter [Angeben der Clientanwendungen, die zum Anmelden bei Lync Server 2013 verwendet werden können](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## So weisen Sie eine Clientversionsrichtlinie auf Benutzerebene zu

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
    > Wenn Sie dieselbe benutzerbasierte Clientversionsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Clientversionsrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]
    > Da Sie im Dialogfeld <STRONG>Richtlinien zuweisen</STRONG> mehrere Richtlinien konfigurieren können, wird die Option <STRONG>&lt;Beibehalten&gt;</STRONG> für alle Richtlinien im Dialogfeld standardmäßig aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Lassen Sie eine automatische Auswahl der globalen Richtlinie oder, falls definiert, der Richtlinie auf Standort- oder Poolebene durch Lync Server zu.
    
      - Klicken Sie auf der Seite **Clientversionsrichtlinie** auf den Namen einer Clientversionsrichtlinie auf Benutzerebene, die Sie zuvor definiert haben.
        

        > [!TIP]
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## So weisen Sie eine Clientversionsrichtlinie auf Benutzerebene mithilfe von Lync Server-Verwaltungsshell-Cmdlets zu.

Sie können Clientversionsrichtlinien auf Benutzerebene mithilfe des **Grant-CsClientVersionPolicy**-Cmdlets zuweisen. Dieses Cmdlet können Sie entweder in der Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell.

## So weisen Sie eine Clientversionsrichtlinie auf Benutzerebene einem einzelnen Benutzer zu

  - Mit dem folgenden Befehl weisen Sie die auf Benutzerebene geltende Clientversionsrichtlinie **RedmondClientVersionPolicy** dem Benutzer Ken Myer zu.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## So weisen Sie eine Clientversionsrichtlinie auf Benutzerebene mehreren Benutzern zu

  - Mit diesem Befehl weisen Sie die auf Benutzerebene geltende Clientversionsrichtlinie **RedmondClientVersionPolicy** allen Benutzern zu, denen derzeit die VoIP-Richtlinie **RedmondVoicePolicy** zugeordnet ist. Weitere Informationen zu dem in diesem Befehl verwendeten **Filter**-Parameter finden Sie in der Dokumentation zum [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlet.
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## So heben Sie die Zuweisung einer Clientversionsrichtlinie auf Benutzerebene auf

  - Mit dem folgenden Befehl heben Sie die Zuweisung einer auf Benutzerebene geltenden Clientversionsrichtlinie auf, die zuvor Ken Myer zugewiesen war. Nach der Aufhebung der Zuweisung wird Ken Myer automatisch mit der globalen Richtlinie, seiner lokalen Standortrichtlinie (sofern vorhanden) oder der Richtlinie auf Dienstebene verwaltet, die seiner Registrierung zugewiesen ist. Eine Richtlinie auf Dienstebene hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie in dem Hilfethema zum [Grant-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientVersionPolicy)-Cmdlet.

## Siehe auch

#### Weitere Ressourcen

[Zuweisen von Richtlinien auf Benutzerebene](lync-server-2013-assigning-per-user-policies.md)  
[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

