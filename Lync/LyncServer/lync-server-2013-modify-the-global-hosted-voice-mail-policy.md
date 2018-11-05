---
title: Ändern der globalen Richtlinie für gehostete Voicemail
TOCTitle: Ändern der globalen Richtlinie für gehostete Voicemail
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412994(v=OCS.15)
ms:contentKeyID: 49295848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern der globalen Richtlinie für gehostete Voicemail

 

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Die neue *globale* Richtlinie für gehostete Voicemail wird zusammen mit Lync Server 2013 installiert. Sie können diese Richtlinie Ihren Anforderungen entsprechend ändern, Sie können sie jedoch weder umbenennen noch löschen. Wenn Sie die globale Richtlinie ändern möchten, verwenden Sie das Cmdlet "Set-CsHostedVoicemailPolicy", um die Parameter auf die für Ihre spezielle Bereitstellung geeigneten Werte zu setzen.

Ausführliche Informationen zum Cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy) finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

## So ändern Sie die globale Richtlinie für gehostete Voicemail

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsHostedVoicemailPolicy" aus, um die Parameter der globalen Richtlinie für Ihre Umgebung festzulegen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Da dieser Befehl den Parameter "Identity" der Richtlinie nicht festlegt, setzt die Windows PowerShell-Befehlszeilenschnittstelle folgende Werte in der globalen Richtlinie für gehostete Voicemail:
    
      - **Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.
    
      - **Organization** gibt eine durch Trennzeichen getrennte Liste der Exchange-Mandanten an, die Lync Server-Benutzer verwalten. Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.
    

    > [!NOTE]
    > Im vorherigen Cmdlet-Beispiel ersetzt der Wert "corp1.litwareinc.com" einen beliebigen Wert, der im Parameter "Organization" möglicherweise bereits vorhanden ist. Wenn die Richtlinie beispielsweise bereits eine durch Trennzeichen getrennte Liste mit Organisationen enthält, wird die gesamte Liste ersetzt. Wenn Sie nicht die gesamte Liste ersetzen, sondern der Liste eine Organisation hinzufügen möchten, führen Sie einen Befehl wie den folgenden aus.

    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

