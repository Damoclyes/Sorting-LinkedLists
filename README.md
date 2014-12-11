Sorting-LinkedLists
===================

Need Help with this insort code


@Override
	public boolean insort(StudentIF s) {
	    StudentLLNode curr = head;

	    if (s == null) {
	        return false;
	    }
	    if (head == null) {
	        StudentLLNode student = new StudentLLNode(s);
	        head = student;
	        size++;
	        //System.out.println("working");
	        return true;
	    } else {
	        if (curr.getStd().compareTo(s) == 0) {
	            return false;
	        }
	        
	        Map<Integer, StudentLLNode> tcur = new TreeMap<Integer, StudentLLNode>();
	        tcur.put(curr.getStd().getId(), curr);
	        while (curr.getNext() != null) {
	            curr = curr.getNext();
	            if(curr.getStd().compareTo(s) == 0) {
	            	return false;
	            }
	            tcur.put(curr.getStd().getId(), curr);
	        }
	        curr.setNext(new StudentLLNode(s));
	        tcur.put(curr.getStd().getId(), curr.getNext());
	        //System.out.println(s.getName() + " " + s.getId());
	        ArrayList<StudentLLNode> bs = new ArrayList<StudentLLNode>();
	        Iterator it = tcur.entrySet().iterator();
	        while(it.hasNext()) {
	        	Map.Entry pairs = (Map.Entry)it.next();
	        	StudentLLNode sss = (StudentLLNode) pairs.getValue();
	        	bs.add(sss);
	        	it.remove();
	        }
	        
	        for(int i = 0; i < bs.size(); i++) {
	        	//bs.get(i).setNext(bs.get(i + 1));
	        	if(i == bs.size() - 1) {
	        		//bs.get(i).setNext(null);
	        	} else {
	        		//bs.get(i).setNext(bs.get(i + 1));
	        	}
	        	//System.out.println("\t" + bs.get(i).toString() + " NET " + bs.get(i).getNext() );
	        }
	        
	        //Collections.sort();
	        
	        //bs.get(bs.size() - 1).setNext(null);
	        //confused here
	        /*StudentLLNode student1 = new StudentLLNode(s);
	        curr.setNext(student1);*/
	        size++;
	        return true;
	    }
	}
