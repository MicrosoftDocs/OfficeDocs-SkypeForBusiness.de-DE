---
title: Konfigurieren einer SNMP-Anwendung in Lync Server 2013
TOCTitle: Konfigurieren einer SNMP-Anwendung in Lync Server 2013
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412972(v=OCS.15)
ms:contentKeyID: 49295341
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer SNMP-Anwendung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Lync Server 2013 enthält eine standardmäßige Webdienstschnittselle, über die Sie den Standortinformationsdienst mit SNMP-Anwendungen (Simple Network Management Protocol) verbinden können, die MAC-Adressen mit Port- und Switchinformationen abgleichen.

Wenn eine SNMP-Anwendung installiert ist und der Standortinformationsdienst keine Übereinstimmung in der Standortdatenbank findet, fragt der Standortinformationsdienst automatisch die Anwendung ab. Dabei wird die vom Client bereitgestellte MAC-Adresse verwendet. Der Standortinformationsdienst verwendet anschließend die von der SNMP-Anwendung zurückgegebenen Port- und Switchinformationen, um erneut eine Abfrage in der Standortdatenbank auszuführen.

Ausführliche Informationen finden Sie unter [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration).


> [!NOTE]
> MAC-Adressen sind auf Computern unter Windows&nbsp;8 nicht verfügbar.



## So konfigurieren Sie die URL für die SNMP-Anwendung

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>"

