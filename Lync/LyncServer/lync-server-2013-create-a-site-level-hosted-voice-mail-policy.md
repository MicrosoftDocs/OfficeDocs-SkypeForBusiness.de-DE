---
title: Erstellen einer Standortrichtlinie für gehostete Voicemail
TOCTitle: Erstellen einer Standortrichtlinie für gehostete Voicemail
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398216(v=OCS.15)
ms:contentKeyID: 49293261
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer Standortrichtlinie für gehostete Voicemail

 

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Eine *Standortrichtlinie* kann sich auf alle Benutzer auswirken, die an dem Standort verwaltet werden, für den die Richtlinie definiert wurde. Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste konfiguriert ist, ihm jedoch keine Benutzerrichtlinie zugewiesen wurde, findet die Standortrichtlinie Anwendung. Wenn Sie keine Standortrichtlinie bereitgestellt haben, wird die globale Richtlinie angewendet.

Ausführliche Informationen zum Konfigurieren von Standortrichtlinien finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu den folgenden Cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## So erstellen Sie eine Standortrichtlinie für gehostete Voicemail

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsHostedVoicemailPolicy" aus, um die Richtlinie zu erstellen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    In diesem Beispiel wird eine Richtlinie für gehostete Voicemail auf Standortebene erstellt. Hierbei werden die folgenden Parameter festgelegt:
    
      - **Identity** gibt eine eindeutige ID für die Richtlinie an, die den Bereich einschließt. Für eine Richtlinie auf Standortebene muss der Parameter "Identity" im Format `site:`*\<Name\>* angegeben werden, beispielsweise `site:Redmond`.
    
      - **Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.
    
      - **Description** stellt eine optionale Beschreibung zur Richtlinie bereit.
    
      - **Organization** gibt eine durch Trennzeichen getrennte Liste der Exchange-Mandanten an, die Lync Server 2013-Benutzer verwalten. Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.

