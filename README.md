# evcplus
import java.util.Scanner; //yuusuf jamac xashi.id: c6230204
public class evcPlus {
    public static void main(String[] args) {
        Scanner akhri = new Scanner(System.in);
        
        // Xogta sirta ah
        final int PIN_CODE = 7711;
        final int AKOON_NUMBER = 615191903;
        final int GANACSI_ID = 2334;
        final int BIIL_REF = 100;

        // Lacagaha xisaabta
        int mobileLacag = 8200;
        int bankLacag = 7900;

        // Bilowga adeegga
        System.out.println(" ");
        String furahaIsticmaal = akhri.nextLine();

        if (!furahaIsticmaal.equals("*770#")) {
            System.out.println("Furaha aad galisay waa khalad.");
            return;
        }

        System.out.println("-EVCPLUS-\nFadlan geli PIN-kaaga (Enter PIN): ");
        int laGeliyayPin = akhri.nextInt();

        if (laGeliyayPin != PIN_CODE) {
            System.out.println("PIN-ka aad gelisay waa khalad.");
            return;
        }

        // Liiska adeegyada
        System.out.println("EVCPlus\n" +
                "1. Fiiri haraaga\n" +
                "2. Ku shubo/ugu shub airtime\n" +
                "3. Bixi biil\n" +
                "4. Wareeji lacag\n" +
                "5. Warbixin kooban\n" +
                "6. Adeegga bangiga\n" +
                "7. Maareynta\n" +
                "8. Bill Payment\n");

        int doorasho = akhri.nextInt();

        if (doorasho < 1 || doorasho > 9) {
            System.out.println("Fadlan dooro tiro sax ah.");
            return;
        }

        switch (doorasho) {
            case 1:
                // Haraaga
                System.out.println("Haraaga EVC-gaagu waa: $" + mobileLacag);
                break;

            case 2:
                // Airtime
                System.out.println("Airtime:\n1. Ku shubo naftaada\n2. Ugu shub qof kale");
                int airtimeDoorasho = akhri.nextInt();

                if (airtimeDoorasho == 1) {
                    // Ku shubo naftaada
                    System.out.print("Geli qadarka: ");
                    int qadarka = akhri.nextInt();

                    if (qadarka > 0 && qadarka <= mobileLacag) {
                        System.out.println("Ma hubtaa inaad $" + qadarka + " ku shubato naftaada?\n1. Haa\n2. Maya");
                        int xaqiijin = akhri.nextInt();

                        if (xaqiijin == 1) {
                            mobileLacag -= qadarka;
                            System.out.println("Waad ku shubatay $" + qadarka + ". Haraaga: $" + mobileLacag);
                        } else {
                            System.out.println("Hawlgalka waa la joojiyay.");
                        }
                    } else {
                        System.out.println("Haraagaagu kuguma filna.");
                    }

                } else if (airtimeDoorasho == 2) {
                    // Ugu shub qof kale
                    System.out.print("Geli nambarka qofka: ");
                    int qofkaNumber = akhri.nextInt();

                    System.out.print("Geli qadarka: ");
                    int qadarka = akhri.nextInt();

                    if (qadarka > 0 && qadarka <= mobileLacag) {
                        System.out.println("Ma hubtaa inaad $" + qadarka + " ugu shubto " + qofkaNumber + "?\n1. Haa\n2. Maya");
                        int xaqiijin = akhri.nextInt();

                        if (xaqiijin == 1) {
                            mobileLacag -= qadarka;
                            System.out.println("Waad ugu shubtay $" + qadarka + " qofka lambarkiisu yahay " + qofkaNumber);
                        } else {
                            System.out.println("Hawlgalka waa la joojiyay.");
                        }
                    } else {
                        System.out.println("Haraagaagu kuguma filna.");
                    }

                } else {
                    System.out.println("Doorasho aan sax ahayn.");
                }
                break;

            case 3:
                // Biil bixin
                System.out.println("1. Eeg biilka\n2. Bixi dhammaan\n3. Bixi qayb");
                int biilDoorasho = akhri.nextInt();

                System.out.print("Geli bill reference number: ");
                int ref = akhri.nextInt();

                if (ref != BIIL_REF) {
                    System.out.println("Bill reference-ka sax ma aha.");
                    break;
                }

                if (biilDoorasho == 1) {
                    System.out.println("Haraagaaga bill-ka waa $" + mobileLacag);
                } else if (biilDoorasho == 2 || biilDoorasho == 3) {
                    System.out.print("Geli qadarka: ");
                    int lacag = akhri.nextInt();

                    if (lacag <= mobileLacag) {
                        System.out.println("Ma hubtaa inaad bixiso $" + lacag + "?\n1. Haa\n2. Maya");
                        int xaqiijin = akhri.nextInt();

                        if (xaqiijin == 1) {
                            mobileLacag -= lacag;
                            System.out.println("Waxaad bixisay $" + lacag + ". Haraagaaga: $" + mobileLacag);
                        } else {
                            System.out.println("Waad ka laabatay.");
                        }
                    } else {
                        System.out.println("Lacagta kuma filna.");
                    }
                } else {
                    System.out.println("Doorasho khaldan.");
                }
                break;

            case 4:
                // Wareeji lacag
                System.out.print("Geli nambarka qofka aad lacag u wareejinayso: ");
                int nambarkaQofka = akhri.nextInt();

                System.out.print("Geli qadarka lacagta: ");
                int lacag = akhri.nextInt();

                if (lacag > mobileLacag) {
                    System.out.println("Haraagaagu kuguma filna.");
                    break;
                }

                System.out.println("Ma hubtaa inaad $" + lacag + " u wareejiso " + nambarkaQofka + "?\n1. Haa\n2. Maya");
                int xaqiijin = akhri.nextInt();

                if (xaqiijin == 1) {
                    mobileLacag -= lacag;
                    System.out.println("Waxaad u wareejisay $" + lacag + " qofka lambarkiisu yahay " + nambarkaQofka);
                    System.out.println("Haraagaaga hadda waa: $" + mobileLacag);
                } else {
                    System.out.println("Hawlgalka waa la joojiyay.");
                }
                break;

            case 6:
                // Adeegga bangiga
                System.out.println("Adeegga bangiga: Haraagaaga bankigu waa $" + bankLacag);
                break;

            default:
                // Adeegyo kale
                System.out.println("Adeegan lama heli karo hadda.");
        }

        akhri.close(); // Scanner xidhid
    }
}


//yuusuf jamac xashi.id: C6230204//
