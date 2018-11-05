---
title: 'Lync Server 2013: Aktivieren von Benutzern für Enterprise-VoIP'
TOCTitle: Aktivieren von Benutzern für Enterprise-VoIP
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413011(v=OCS.15)
ms:contentKeyID: 49295870
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Nachdem Sie Dateien für einen oder mehrere Vermittlungsserver installiert, das Routing ausgehender Anrufe konfiguriert und optional eine oder mehrere erweiterte Enterprise-VoIP-Features bereitgestellt haben, können Sie die folgenden Schritte ausführen, um festzulegen, dass ein Benutzer Anrufe mit Enterprise-VoIP ausführen kann:


> [!NOTE]
> Von den nachfolgend beschriebenen Verfahren kann nur das erste mit der Lync Server-Systemsteuerung ausgeführt werden. Die weiteren Verfahren können nur mit der Lync Server-Verwaltungsshell ausgeführt werden.



  - Aktivieren des Benutzerkontos für Enterprise-VoIP.

  - (Optional) Zuweisen einer benutzerspezifischen VoIP-Richtlinie für das Benutzerkonto.

  - (Optional) Zuweisen eines benutzerspezifischen Satzes mit Wähleinstellungen für das Benutzerkonto.

## So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** .

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen** .

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das für Enterprise-VoIP aktiviert werden soll.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen** .

7.  Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf **Enterprise-VoIP** .

8.  Klicken Sie auf **Anschluss-URI** , und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).

9.  Klicken Sie auf **Commit** .

Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, müssen Sie sicherstellen, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen wurde. Es spielt hierbei keine Rolle, ob diese Zuweisung auf global Ebene (standardmäßige Zuweisung) oder benutzerspezifisch erfolgt.

Standardmäßig werden allen Benutzern eine globale VoIP-Richtlinie und ein Wählplan zugeweisen. Wenn auf Standortebene eine VoIP-Richtlinie für den Standort vorhanden ist, der das Benutzerkonto verwaltet, gelten diese Standortrichtlinien automatisch für alle Benutzer. Führen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** aus, um eine benutzerspezifische VoIP-Richtlinie oder einen Wählplan für einen Benutzer anzuwenden. Ausführliche Informationen finden Sie in der Dokumentation zu [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Zuweisen einer VoIP-Richtlinie

Globale VoIP-Richtlinien und VoIP-Richtlinien für einen Standort werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind. Sie können auch VoIP-Richtlinien erstellen, die für spezielle Benutzer oder Gruppen gelten. Diese benutzerbezogenen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden. Wenn Sie die globale VoIP-Richtlinie oder eine VoIP-Richtlinie für einen Standort für alle Benutzer mit Aktivierung für Enterprise-VoIP verwenden möchten, können Sie diesen Abschnitt überspringen und mit dem Abschnitt Zuweisen eines Wählplans weiter unten in diesem Thema fortfahren.

## So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie namens **VoicePolicyJapan** zugewiesen.

Ausführliche Informationen zum Zuweisen einer benutzerspezifischen VoIP-Richtlinie sowie zum Ausführen des Cmdlets **Grant-CsVoicePolicy** finden Sie in der Dokumentation zur [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Zuweisen eines Wählplans

Zum Abschließen der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen Sie dem Benutzer einen Wählplan zuweisen. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht jedem Benutzer explizit einen vorhandenen Wählplan zuweisen. Wenn Sie den globalen Wählplan oder den Wählplan auf Standortebene für alle Benutzer mit Aktivierung für Enterprise-VoIP verwenden möchten, können Sie diesen Abschnitt überspringen.

## So weisen Sie einen Wählplan zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einen benutzerspezifischen Wählplan zuzuweisen:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly der Benutzerwählplan mit der Bezeichnung **DialPlanJapan** zugewiesen.

Ausführliche Informationen zum Zuweisen eines Benutzerwählplans oder zum Ausführen des **Grant-CsDialPlan**-Cmdlets finden Sie in der Dokumentation zur [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Siehe auch

#### Aufgaben

[Deaktivieren eines Benutzers für Enterprise-VoIP](lync-server-2013-disable-a-user-for-enterprise-voice.md)

