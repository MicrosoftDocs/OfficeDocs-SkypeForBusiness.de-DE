---
title: 'Lync Server 2013: Konfigurieren von VoIP-Routen für ausgehende Anrufe'
TOCTitle: Konfigurieren von VoIP-Routen für ausgehende Anrufe
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425890(v=OCS.15)
ms:contentKeyID: 49293742
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von VoIP-Routen für ausgehende Anrufe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Eine Lync Server 2013-VoIP-Route ordnet Zieltelefonnummern einem oder mehreren PSTN-Gateways (Public Switched Telephone Network) oder SIP-Trunks sowie einem oder mehreren PSTN-Verwendungseinträgen zu.

**So zeigen Sie VoIP-Routen in der Lync Server-Systemsteuerung an**

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie auf **VoIP-Routing** .

3.  Klicken Sie auf **Route** .

4.  Doppelklicken Sie auf eine VoIP-Route, um zusätzliche Eigenschaften aus der Liste der VoIP-Routen anzuzeigen, oder wählen Sie die Route aus, und klicken Sie auf **Bearbeiten** . Klicken Sie dann auf **Details anzeigen** .
    

    > [!NOTE]
    > Sie können nur jeweils für eine einzelne Route Detailinformationen anzeigen.



**So zeigen Sie VoIP-Routen in der Windows PowerShell an**

  - Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.VoIP-Routen können mit Windows PowerShell und dem Cmdlet **Get-CsVoiceRoute** angezeigt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder eine Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Geben Sie zum Anzeigen von Informationen zu allen VoIP-Routen den folgenden Befehl in die Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsVoiceRoute
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :


> [!NOTE]
> Ausführliche Informationen finden Sie unter <A href="lync-server-2013-voice-routes.md">VoIP-Routen in Lync Server 2013</A> in der Planungsdokumentation.



## In diesem Abschnitt

  - [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

## Siehe auch

#### Weitere Ressourcen

[Verwalten des VoIP-Routings in Lync Server 2013](lync-server-2013-managing-voice-routing.md)

