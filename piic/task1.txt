(setf vara (make-array '(4 3)))
(setf varb (make-array '(4 3)))
(setf varc (make-array '(4 3)))


(print "Array1:")
(terpri)


(dotimes (k 4)
    (dotimes (l 3)
        (setf (aref vara k l) (read))
    )
)

(print "Array2:")
(terpri)


(dotimes (k 4)
    (dotimes (l 3)
        (setf (aref varb k l) (read))
    )
)


(dotimes (k 4)
    (dotimes (l 3)
        (if (>= (aref vara k l) (aref varb k l)) 
            (setf (aref varc k l) (aref vara k l))
        )
        (if (< (aref vara k l) (aref varb k l))
            (setf (aref varc k l) (aref varb k l))
        )
    )
)


(defun print-2d-array-as-table (array)
  (loop for k from 0 below (array-dimension array 0)
        do (loop for l from 0 below (array-dimension array 1)
                 do (princ (aref array i l))
                    (if (= l (1- (array-dimension array 1)))
                        (terpri)
                        (princ #\Space)))))


(print-2d-array-as-table varc)




