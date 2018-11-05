---
title: Erstellen einer Benutzerrichtlinie für gehostete Voicemail
TOCTitle: Erstellen einer Benutzerrichtlinie für gehostete Voicemail
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425867(v=OCS.15)
ms:contentKeyID: 49293703
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer Benutzerrichtlinie für gehostete Voicemail

 

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Eine Richtlinie auf *Benutzerebene* wirkt sich ausschließlich auf einzelne Benutzer, Gruppen und Kontaktobjekte aus. Zum Bereitstellen einer Richtlinie auf Benutzerebene müssen Sie die Richtlinie explizit auf einen oder mehrere Benutzer, Gruppen oder Kontaktobjekte anwenden. Ausführliche Informationen finden Sie unter [Zuweisen einer Benutzerrichtlinie für gehostete Voicemail](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Ausführliche Informationen zum Arbeiten mit Richtlinien für gehostete Voicemail auf Benutzerebene finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## So erstellen Sie eine Richtlinie für gehostete Voicemail auf Benutzerebene

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsHostedVoicemailPolicy" aus, um die Richtlinie zu erstellen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    In diesem Beispiel wird eine Richtlinie für gehostete Voicemail auf Benutzerebene erstellt. Hierbei werden die folgenden Parameter festgelegt:
    
      - **Identity** gibt eine eindeutige ID für die Richtlinie an, die den Bereich einschließt. Für eine Richtlinie auf Benutzerebene wird dieser Parameterwert als einfache Zeichenfolge angegeben, z. B. "ExRedmond".
    
      - **Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.
    
      - **Description** stellt eine optionale Beschreibung zur Richtlinie bereit.
    
      - **Organization** gibt eine durch Trennzeichen getrennte Liste der Exchange-Mandanten an, die Lync Server 2013-Benutzer verwalten. Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.

## Siehe auch

#### Aufgaben

[Zuweisen einer Benutzerrichtlinie für gehostete Voicemail](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

