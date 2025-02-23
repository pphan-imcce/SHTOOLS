# MakeMagGridPoint()

Determine the three components of the magnetic field vector at a single point.

# Usage

value = MakeMagGridPoint (cilm, a, r, lat, lon, [lmax, dealloc])

# Returns

value : float, dimension (3)
:   Vector components (r, theta, phi) of the magnetic field at (r, lat, lon).

# Parameters

cilm : float, dimension (2, lmaxin+1, lmaxin+1)
:   The real Schmidt semi-normalized spherical harmonic coefficients of the magnetic potential. The coefficients C0lm and C1lm refer to the cosine (Clm) and sine (Slm) coefficients, respectively, with Clm=cilm[0,1,m] and Slm=cilm[1,l,m].

a: float
:   The reference radius of the spherical harmonic coefficients.

r: float
:   The radius to evaluate the magnetic field.

lat : float
:   The latitude of the point in degrees.

lon : float
:   The longitude of the point in degrees.

lmax : optional, integer, default = lmaxin
:   The maximum spherical harmonic degree used in evaluating the function.

dealloc : optional, integer, default = 0
:   0 (default) = Save variables used in the external Legendre function calls. (1) Deallocate this memory at the end of the funcion call.

# Description

MakeMagGridPoint will compute the three components of the magnetic field vector at a single point. The input latitude and longitude are in degrees, and the output components are in spherical coordinates (r, theta, phi). The magnetic potential is given by

`V = a Sum_{l=0}^lmax (a/r)^(l+1) Sum_{m=-l}^l C_{lm} Y_{lm}`,

and the vector magnetic field is

`B = - Grad V`.

The coefficients are referenced to a radius a, and the output values have the same units as the input spherical harmonic coefficients.
