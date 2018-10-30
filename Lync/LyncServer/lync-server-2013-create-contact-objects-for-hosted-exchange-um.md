---
title: 'Lync Server 2013: Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste'
TOCTitle: Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412765(v=OCS.15)
ms:contentKeyID: 49294965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Das folgende Verfahren erläutert die Erstellung von Kontaktobjekten der automatischen Telefonzentrale oder des Teilnehmerzugriffs für gehostetes Exchange Unified Messaging (UM).

Ausführliche Informationen finden Sie unter [Kontaktobjektverwaltung für gehostete Exchange-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in der Planungsdokumentation.

Ausführliche Informationen zum Konfigurieren von Kontaktobjekten finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu den folgenden Cmdlets:

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)


> [!IMPORTANT]
> Bevor Lync Server 2013-Kontaktobjekte für gehostete Exchange UM-Dienste aktiviert werden können, muss eine Richtlinie für gehostete Voicemail erstellt werden, die auf diese Objekte angewendet werden kann. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in Lync Server 2013</A>.



## So erstellen Sie Kontaktobjekte für die automatische Telefonzentrale oder den Teilnehmerzugriff für gehostete Exchange UM-Dienste

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsExUmContact" zum Erstellen von Kontaktobjekten aus, die für Ihre Bereitstellung erforderlich sind. Führen Sie beispielsweise folgenden Befehl aus, um ein Kontaktobjekt für die automatische Telefonzentrale und den Teilnehmerzugriff zu erstellen:
    
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True

       &nbsp;
    
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
    
    In diesen Beispielen werden folgende Parameter festgelegt:
    
      - **SipAddress** gibt die SIP-Adresse des Kontaktobjekts an. Hierbei muss es sich um eine Adresse handeln, die noch nicht zur Konfiguration eines Benutzer- oder Kontaktobjekts in den Active Directory-Domänendiensten verwendet wurde. Der Wert muss, den vorherigen Beispielen entsprechend, im Format "sip:\< *SIP-Adresse* \>" vorliegen.
    
      - **RegistrarPool** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools, in dem der Registrierungsdienst ausgeführt wird.
        

        > [!NOTE]
        > Exchange UM-Kontaktobjekte können nicht in Pools verschoben werden, die Bestandteile von Lync Server 2013-Bereitstellungen vor Lync Server 2013 sind.

    
      - **OU** gibt die Active Directory-Organisationseinheit an, in der dieses Kontaktobjekt abgelegt wird.
    
      - **DisplayNumber** gibt die Rufnummer des Kontaktobjekts an. Die Rufnummer muss für jedes Kontaktobjekt eindeutig sein.
    
      - **AutoAttendant** gibt an, ob es sich bei diesem Kontaktobjekt um eine automatische Telefonzentrale handelt. Eine automatische Telefonzentrale stellt eine Reihe von Ansagen bereit, über die Anrufer innerhalb des Telefonsystems navigieren und den gewünschten Gesprächspartner erreichen können. Der Wert **False** (Standard) für diesen Parameter weist auf ein Teilnehmerzugriff-Kontaktobjekt hin.

