# Publish Container

Docker Push ist ein Befehl, der verwendet wird, um ein lokales Docker-Image oder ein Repository an ein zentrales Repository zu pushen oder freizugeben. Dabei kann es sich um eine öffentliche Registry wie https://hub.docker.com, eine private Registry oder eine selbst gehostete Registry handeln. Wir müssen uns bei der Registry anmelden, bevor wir das Docker-Image in die Registry schieben.
> docker login -u username --password-stdin

Die Daten, die an die Registry übertragen werden, werden komprimiert, bevor sie an die Registry gesendet werden. Der Daemon überträgt standardmäßig fünf Schichten eines Abbilds auf einmal. Dies kann jedoch mit der Option "-max-concurrent-uploads" geändert werden, während das Docker-Abbild an die Registry übertragen wird.

>`$docker push [OPTIONS] NAME[:TAG]`

 Um das Image in unsere private Registry zu übertragen, müssen wir unser Image mit dem Hostnamen des Rechners, auf dem die Registry läuft, neu kennzeichnen.

Nach erfolgreichem Push befindet sich der Container unter https://devsecops.emceeo.de/itsec_ss22_csharps/cicdprojekt1/container_registry:
![[Pasted image 20220607111111.png]]