# GLQGridCoord()

Compute the latitude and longitude coordinates used in Gauss-Legendre quadrature grids.

# Usage

latglq, longlq = GLQGridCoord (lmax, [extend])

# Returns

latglq : float, dimension (lmax+1)
:   The latitude coordinates of a Gauss-Legendre quadrature grid in degrees.

longlq : float, dimension (nlong)
:   The longitude coordinates of a Gauss-Lengendre quadrature grid in degrees, dimensioned as (2\*lmax+1) when extend is 0 or (2\*lmax+2) when extend is 1.

# Parameters

lmax : integer
:   The maximum spherical harmonic degree that will be integrated exactly by Gauss-Legendre quadrature.

extend : input, optional, bool, default = False
:   If True, include 360 E longitude.

# Description

GLQGridCoord will compute the latitude and longitude coordinates that are used in Gauss-Legendre quadrature grids for performing spherical harmonic transforms and reconstructions. The latitudinal nodes correspond to the zeros of the Legendre polynomial of degree lmax+1, and the longitudinal nodes are equally spaced with an interval of 360/(2*lmax+1) degrees.
