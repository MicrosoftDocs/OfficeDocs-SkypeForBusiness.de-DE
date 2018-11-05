---
title: Zuweisen einer VoIP-Richtlinie auf Benutzerebene
TOCTitle: Zuweisen einer VoIP-Richtlinie auf Benutzerebene
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49890863
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer VoIP-Richtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Globale VoIP-Richtlinien und VoIP-Richtlinien für einen Standort werden automatisch allen Lync Server 2013-Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind. Sie können mithilfe der Systemsteuerung für Lync Server 2013 oder der Verwaltungsshell für Lync Server 2013 VoIP-Richtlinien auch bestimmten Benutzern zuweisen. Anhand der in diesem Thema beschriebenen Verfahren können Sie Lync Server-Benutzern explizit Benutzerrichtlinien zuweisen.

## So weisen Sie mit der Lync Server-Systemsteuerung eine benutzerspezifische VoIP-Richtlinie zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **VoIP-Richtlinie** die Benutzerrichtlinie aus, die Sie anwenden möchten.
    

    > [!NOTE]
    > Mit den Einstellungen <STRONG>&lt;Automatisch&gt;</STRONG> werden die Standardeinstellungen des Servers oder die globalen Richtlinieneinstellungen angewendet.



## So weisen Sie mit der Lync Server-Verwaltungsshell eine benutzerspezifische VoIP-Richtlinie zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie namens **VoicePolicyJapan** zugewiesen.

Ausführliche Informationen zum Zuweisen einer benutzerspezifischen VoIP-Richtlinie sowie zum Ausführen des Cmdlets **Grant-CsVoicePolicy** finden Sie in der Dokumentation zur [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Zuweisen einer benutzerbasierten VoIP-Richtlinien mithilfe von Windows PowerShell-Cmdlets

Benutzerbasierte VoIP-Richtlinien können auch mithilfe der Windows PowerShell und des **Grant-CsVoicePolicy**-Cmdlets zugewiesen werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung der Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Zuweisen einer benutzerbasierten VoIP-Richtlinien zu einem einzelnen Benutzer

  - Der folgende Befehl weist die benutzerbasierte VoIP-Richtlinie "RedmondVoicePolicy" dem Benutzer "Ken Myer" zu.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## Zuweisen einer benutzerbasierten VoIP-Richtlinien zu mehreren Benutzern

  - Der folgende Befehl weist die benutzerbasierte VoIP-Richtlinie "FinanceVoicePolicy" allen Benutzern zu, die Konten in der OU "Finance" in Active Directory haben. Weitere Informationen zu dem in diesem Befehl verwendeten Parameter "OU" finden Sie in der Dokumentation zum [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlet.
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## Aufheben der Zuweisung einer benutzerbasierten VoIP-Richtlinie

  - Der folgende Befehl hebt die Zuweisung der dem Benutzer "Ken Myer" zuvor zugewiesenen VoIP-Richtlinie auf. Nachdem die Zuweisung der benutzerbasierten Richtlinie aufgehoben ist, wird Ken Myer automatisch über die globale Richtlinie oder, sofern vorhanden, seine lokale Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)-Cmdlet.

## Siehe auch

#### Aufgaben

[Deaktivieren eines Benutzers für Enterprise-VoIP](lync-server-2013-disable-a-user-for-enterprise-voice.md)  

#### Weitere Ressourcen

[Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md)

