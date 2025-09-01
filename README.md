package neverland;

public class EverLand {
	private static final int ADULT_PRICE = 80000;
	private static final int YOUTH_PRICE = 50000;
	private static final int BABY_PRICE = 30000;

	private static final String ADULT_TYPE = "성인";
	private static final String YOUTH_TYPE = "청소년";
	private static final String BABY_TYPE = "아이";

	public static void main(String[] args) {
		Ticket[] tArr = new Ticket[54300];

		int adultIndex = 0;
		int youthIndex = 0;
		int babyIndex = 0;
		Ticket[] adultArr = new Ticket[54300];
		Ticket[] youthArr = new Ticket[54300];
		Ticket[] babyArr = new Ticket[54300];

		double sum = 0;

		for (int i = 0; i < 54300; i++) {
			String type = null;
			Ticket ticket = null;
			if (54000 > i) {
				if (0 == i + 1 % 3) {
					sum += YOUTH_PRICE;
					type = YOUTH_TYPE;
					ticket = new Ticket(i + 1, type, YOUTH_PRICE);
					youthArr[youthIndex++] = ticket;
				} else {
					sum += ADULT_PRICE;
					type = ADULT_TYPE;
					ticket = new Ticket(i + 1, type, ADULT_PRICE);
					adultArr[adultIndex++] = ticket;
				}
			} else {
				sum += BABY_PRICE;
				type = BABY_TYPE;
				ticket = new Ticket(i + 1, type, BABY_PRICE);
				babyArr[babyIndex++] = ticket;

			}
			tArr[i] = ticket;
			System.out.printf("%d번째 손님 입장.(%s,%.0f)",(i+1),ticket.getType(),sum);
			System.out.println();
		}

	}

}
