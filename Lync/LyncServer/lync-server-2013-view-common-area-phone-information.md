---
title: Anzeigen von Informationen zu Telefonen in öffentlichen Bereichen
TOCTitle: Anzeigen von Informationen zu Telefonen in öffentlichen Bereichen
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994081(v=OCS.15)
ms:contentKeyID: 52056479
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Telefonen in öffentlichen Bereichen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Mit dem Cmdlet **Get-CsCommonAreaPhone** können Sie Informationen zu Telefonen in öffentlichen Bereichen abrufen, die für die Verwendung in Ihrer Organisation konfiguriert sind. Wenn Sie dieses Cmdlet ohne Parameter aufrufen, gibt es Informationen zu allen Ihren Telefonen in öffentlichen Bereichen zurück. Mit optionalen Parametern haben Sie verschiedene Möglichkeiten, Informationen zu filtern. Sie können beispielsweise alle Telefone in öffentlichen Bereichen zurückgeben, die Kontaktobjekte in einer angegebenen Organisationseinheit haben, oder alle Kontaktobjekte, die sich in einem bestimmten Gebäude befinden. Nähere Informationen zu **Get-CsCommonAreaPhone**-Parametern finden Sie unter [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone).

Führen Sie das Cmdlet **Get-CsCommonAreaPhone** entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell aus.


## Anzeigen von Information zu allen Ihren Telefonen in öffentlichen Bereichen

  - Zum Anzeigen von Information zu allen Ihren Telefonen in öffentlichen Bereichen geben Sie folgenden Befehl in die Lync Server-Verwaltungsshell ein und drücken dann die Eingabetaste:
    
        Get-CsCommonAreaPhone
    
    Daraufhin werden ähnliche Informationen wie die folgenden zurückgegeben:
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone).

