---
title: 'Lync Server 2013: Definieren eines PSTN-Gateways für eine Zweigstelle'
TOCTitle: Definieren eines PSTN-Gateways für eine Zweigstelle
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398689(v=OCS.15)
ms:contentKeyID: 49294653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren eines PSTN-Gateways für eine Zweigstelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Führen Sie dieses Verfahren am zentralen Standort aus, der mindestens einen Front-End-Pool oder Standard Edition-Server umfasst.


> [!IMPORTANT]
> Stellen Sie vor dem Ausführen dieser Schritte sicher, dass die folgenden Bedingungen erfüllt sind: 
> <UL>
> <LI>
> <P>Die Lync Server 2013- Kommunikationssoftware muss am zentralen Standort eingerichtet sein.</P>
> <LI>
> <P>Vermittlungsserver muss am zentralen Standort bereitgestellt sein.</P></LI></UL>



## So definieren Sie ein PSTN-Gateway

1.  Klicken Sie auf **Start** , **Alle Programme** , **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator** .

2.  Erweitern Sie in der Konsolenstruktur den zentralen Standort, erweitern Sie **Zweigstellenstandorte** , erweitern Sie anschließend den Namen des Zweigstellenstandorts, für den Sie ein PSTN-Gateway (Public Switched Telephone Network) definieren möchten, und erweitern Sie anschließend **Freigegebene Komponenten** .

3.  Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways** , und klicken Sie dann auf **Neues IP/PSTN-Gateway** .

4.  Klicken Sie im Dialogfeld **Neues IP/PSTN-Gateway definieren** auf **Gateway-FQDN oder IP-Adresse** , und geben Sie den FQDN (Fully Qualified Domain Name) oder die IP-Adresse des Gateways ein, das am Zweigstellenstandort bereitgestellt werden soll.

5.  Klicken Sie auf **Überwachungsport für das IP/PSTN-Gateway** , und akzeptieren Sie die Standardwerte.

6.  Klicken Sie in der Liste **SIP-Transportprotokoll** auf das vom Gateway verwendete Transportprotokoll, und klicken Sie dann auf **OK** .
    

    > [!NOTE]
    > Aus Sicherheitsgründen wird der Einsatz eines PSTN-Gateways mit TLS-Unterstützung (Transport Layer Security) ausdrücklich empfohlen.




> [!TIP]
> Verwenden Sie das Cmdlet <STRONG>Set-CsPstnGateway</STRONG>, um die Eigenschaften eines PSTN-Gateways zu ändern. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A> in der Lync Server-Verwaltungsshell-Hilfe.



Der **nächste Schritt** für Ausfallsicherheit an Zweigstellenstandorten: [Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

## Siehe auch

#### Konzepte

[Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)

