README Comet-PTM
=====================================================

Comet-PTM is a modified version of the Comet project for the thorough analysis of post-translational modifications, developed at the Cardiovascular Proteomics laboratory at CNIC (Spain).<br>
<br>
Here we will describe the details that are different in Comet-PTM, especially the Comet-PTM specific parameters and its output. For the remaining parameters and output common with the original version of Comet, you have complete documentation at http://comet-ms.sourceforge.net/<br>
<br>
Params files used in Comet-PTM are identical to the params file in Comet, with the exception of the following section:<br>
<br>
<tt>#</tt><br>
<tt># CNIC / comet-iq / comet-PTM specific</tt><br>
<tt>#</tt><br>
<tt># do deltaX search for: (-delta_tolerance_outer < deltaMass < -delta_tolerance_inner) OR</tt><br>
<tt>#                       (+delta_tolerance_inner < deltaMass < +delta_tolerance_outer)</tt><br>
<tt>#</tt><br>
<tt>use_delta_xcorr = 1                    # 0=no (default), 1=yes</tt><br>
  <tt>delta_outer_tolerance = 500            # ignored if use_delta_xcorr 0, default 320 </tt><br>
  <tt>delta_inner_tolerance = 0              # ignored if use_delta_xcorr 0, default 0.8</tt><br>
  <tt>use_delta_back_jumps = 0               # 0=no (default), 1=yes</tt><br>
  <tt>use_delta_forward_jumps = 0            # 0=no (default), 1=yes</tt><br>
<tt>dont_calc_pseudo_non_mod = 1           # 0=yes, calculate pseudo nonmod (default), 1=avoid calculating pseudo non_mod</tt><br>
<br>
<br>
<tt>use_delta_xcorr</tt> checks whether the DeltaXCorr (the mass difference between the theoretical mass of the peptide identified and the experimental mass of potentially modified peptides) will be used or not (this is needed to use Comet-PTM).<br>
<tt>delta_outer_tolerance</tt>, the tolerance in Da for the maximum Delta XCorr that should be considered to calculate the mass of the modified peptide.<br>
<tt>delta_inner_tolerance</tt>, the minimum value of the Delta Xcorr, under which a mass difference is not taken into consideration (for being considered a non-modified peptide).<br>
<tt>use_delta_back_jumps</tt>, to consider isotopologues <i>after</i> the peak analyzed.<br>
<tt>use_delta_forward_jumps</tt>, to consider isotopologues <i>before</i> the peak analyzed.<br>
<tt>dont_calc_pseudo_non_mod</tt>, by default the nonmodified peptide is included among search results; by activating this parameter, those peptides will not be presented.<br>
<br>
<br>
[output information to be added]
