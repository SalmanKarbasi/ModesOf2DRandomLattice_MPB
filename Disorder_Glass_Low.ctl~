;Calculating modes of a disordered glass fiber March 2013
;defing the permitivvies of core and clad
;(define-param eps-core 2.2201); 
;(define-param eps-clad 2.5281); 
; setting the backgroung permitivity
;(set! default-material (make dielectric (epsilon eps-clad)))


(set! geometry-lattice (make lattice (size 255 255 no-size)
                         ))
;(set! geometry (list 
;;;
;;;
;))

(set! epsilon-input-file "mpb-eps-NoCladding4590_1_45.h5")

(set! resolution 18)

; Generally, we want omega(k) for a range of k values.  MPB
; can automatically interpolate a set of k values between any
; given bounds.  Here, we will interpolate 10 k's between 0 and 2.
;(define-param kmin 2.84)
(define-param kmax 2.2907) ; nglass=1.45, lam 0.633
;(define-param k-interp 20)
; k-points is the list of k values that MPB computes eigenmodes at.
; (vector3 x y z) specifies a vector.  (k is in units of 2 pi/distance)
;(set! k-points (interpolate k-interp 
;			    (list (vector3 0 0 kmin) (vector3 0 0 kmax))))

(set! k-points (list (vector3 0 0 kmax)))

(set! num-bands 300)

(run output-efield-z)
;(run output-efield-x output-efield-y output-efield-z output-hfield-x 
;output-hfield-y output-hfield-z)

; To plot the output
; mpb-data -r -m 1 epsilon.h5 
; h5topng epsilon.h5
; mpb-data -r -m 1 e.k01.b*.z.h5
; h5topng -C epsilon.h5:data-new -c bluered -Z -d z.r-new e.k01.b*.z.h5
; To Run
; mpirun -np 4 mpb SMF.ctl > SMF.out
