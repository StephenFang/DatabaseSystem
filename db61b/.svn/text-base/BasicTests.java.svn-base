package db61b;
import org.junit.Test;
import static org.junit.Assert.*;

import static db61b.Utils.*; /* NOT SURE IF I should import this to throw the error. */




public class BasicTests {


	@Test
	public void testSizeForRow() {
		Row r = new Row(new String[]{"Josh", "is", "nice."});
		assertEquals(3, r.size());
	}

	@Test
	public void testGetForRow() {
		Row r = new Row(new String[]{"Josh", "is", "nice."});
		String expected = "is";
		String message0 = "There is an error";

		assertEquals(expected, r.get(1));



	}


	@Test
	public void testEqualsForRow() {
		Row r1 = new Row(new String[]{"Josh", "is", "nice."});
		Row r2 = new Row(new String[]{"Josh", "is", "nice."});
		Row r3 = new Row(new String[]{"Josh", "is", "good."});
		Row r4 = new Row(new String[]{"Josh", "is", "good", "and", "nice."});
		String[] r5 = new String[]{"Josh", "is", "nice."};



		assertTrue(r1.equals(r2));
		assertFalse(r1.equals(r3));
		assertFalse(r1.equals(r4));
		assertFalse(r1.equals(r5));

	}


	@Test
	public void testColunmnsForTable() {
		String[] ct = new String[]{"SID", "Name", "Age"};
		Table t1 = new Table(ct);
		assertEquals(3, t1.columns());

	}


	@Test
	public void testGetTitle() {
		String[] ct = new String[]{"SID", "Name", "Age"};
		Table t1 = new Table(ct);
		assertEquals("Name", t1.getTitle(1));
	}

	@Test
	public void testFindColumn() {
		String[] ct = new String[]{"SID", "Name", "Age"};
		Table t1 = new Table(ct);
		assertEquals(2, t1.findColumn("Age"));
		assertEquals(-1, t1.findColumn("GG"));

	}

	@Test
	public void testSizeForTable() {
		String[] ct = new String[]{"SID", "Name", "Age"};
		Table t1 = new Table(ct);
		Row r1 = new Row(new String[]{"001", "Brian", "2"});
		Row r2 = new Row(new String[]{"002", "Austin", "18"});
		Row r3 = new Row(new String[]{"003", "Stephen", "21"});
		t1.add(r1);
		t1.add(r2);
		t1.add(r3);
		assertEquals(3, t1.size());


	}

	@Test
	public void testPrintForTable() {
		String[] ct = new String[]{"SID", "Name", "Age"};
		Table t1 = new Table(ct);
		Row r1 = new Row(new String[]{"001", "Brian", "2"});
		Row r2 = new Row(new String[]{"002", "Austin", "18"});
		Row r3 = new Row(new String[]{"003", "Stephen", "21"});
		t1.add(r1);
		t1.add(r2);
		t1.add(r3);
	}

	@Test
	public void testDatabase() {
		String[] ct1 = new String[]{"SID", "Name", "Age"};
		Table t1 = new Table(ct1);
		Row r1 = new Row(new String[]{"001", "Brian", "2"});
		Row r2 = new Row(new String[]{"002", "Austin", "18"});
		Row r3 = new Row(new String[]{"003", "Stephen", "21"});
		t1.add(r1);
		t1.add(r2);
		t1.add(r3);

		String[] ct2 = new String[]{"CCN", "Department", "Semester"};
		Table t2 = new Table(ct2);
		Row r4 = new Row(new String[]{"123", "EECS", "Fall 2014"});
		Row r5 = new Row(new String[]{"456", "CS", "Spring 2014"});
		Row r6 = new Row(new String[]{"789", "Psychology", "Spring 2015"});
		t2.add(r4);
		t2.add(r5);
		t2.add(r6);

		Database d1 = new Database();
		d1.put("Students", t1);
		d1.put("Schedule", t2);

		assertEquals(t1, d1.get("Students"));
	}

    public static void main(String[] args) {
        System.exit(ucb.junit.textui.runClasses(BasicTests.class));
    }

}